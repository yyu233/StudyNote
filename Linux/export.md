Note that you do need the double quotes after export, because it's an ordinary builtin, not a keyword. This is only true in some shells such as dash, zsh (in sh emulation), yash or posh; bash and ksh both treat export specially.

```
export VAR="$stuff"

```
