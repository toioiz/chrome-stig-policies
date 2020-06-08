# chrome-stig-policies

## Set Up Policies

Policy configuration files live under /etc/chromium for Chromium, and under /etc/opt/chrome for Google Chrome.  There are two sets of policies kept in these directories: one set that is required and mandated by an administrator, and one set that is recommended for users but not required.  These two sets live at:

`/etc/opt/chrome/policies/managed/`
`/etc/opt/chrome/policies/recommended/`

* Create these directories if they do not already exist:

`>mkdir -p /etc/opt/chrome/policies/managed`
`>mkdir -p /etc/opt/chrome/policies/recommended`

Make sure that the files under /managed are not writable by non-admin users; otherwise, they could just overwrite your policies to get the configuration they want!

>chmod -w /etc/opt/chrome/policies/managed
