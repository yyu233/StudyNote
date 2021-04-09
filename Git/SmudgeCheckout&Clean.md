Let’s say you need a secret token in your code inside the config.h file, you want to commit that file to the git repository, but you don’t want it to contain sensible information.

Simplest solution would be to create a placeholder (e.g. {your-secret-token}) that should be updated with the right value (e.g. super-secret-value!) upon checkout:

`const std::string secretToken = "{your-secret-token}";`

# After checkout, the line should be updated to:
const std::string secretToken = "super-secret-value!";

As soon as you update the file to include your secret value, the file will be shown as modified in the git status command.

Thanks to the smudge filter, you can:

   * automate the process, so the file will be updated automatically upon checkout.
   * prevent the file change to be part of the git diff output.

You need two steps for configuring a smudge filter:

   * Identify in .gitattributes file the files that should be processed by the filter. In this simple example we want to process the config.h file using a filter named updateSecretToken:

# .gitattributes file
config.h filter=updateSecretToken

   * Define the smudge filter updateSecretToken, that will substitute the placeholder with your secret. This can be done in the git global configuration:

git config --global filter.updateSecretToken.smudge 'sed "s/{your-secret-token}/super-secret-value!/"'

Next time you checkout the config.h file, its content will be automatically updated and your secret will be included in the file.

# Cleaning your commit

As much as you need to update the config.h file content upon checkout to include your secret, it’s important as well to update the content before including the file in the stage area, and put back {your-secret-token} instead of super-secret-value!. Otherwise, your secret would be exposed.

For doing it, you can define the clean filter updateSecretToken. Similar to the smudge filter, this can be done in the git global config:

git config --global filter.updateSecretToken.clean 'sed "s/super-secret-value!/{your-secret-token}/"'

