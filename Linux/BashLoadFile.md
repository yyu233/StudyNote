1. Bash as login shell will load /etc/profile, ~/.bash_profile, ~/.bash_login, ~/.profile in the order
2. Bash as non-login interactive shell will load ~/.bashrc
3. Bash as non-login non-interactive shell will load the configuration specified in environment variable $BASH_ENV
