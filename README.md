# apple-scripts-scraps

## sleep
Runs actions upon sleeping.

First, modify PATH_TO_FILE in com.cellar.sleepwatcher.plist to point to the file's location within this directory.

Then:

```bash
brew install sleepwatcher        # installs utility for doing things on sleep (among others)
chmod 700 $PWD/sleep/.sleep      # changes permissioning of .sleep file so it is executable
ln -sf $PWD/sleep/com.cellar.sleepwatcher.plist /Library/LaunchDaemons/com.cellar.sleepwatcher.plist  # symlink plist
launchctl load -w /Library/LaunchDaemons/com.cellar.sleepwatcher.plist  # starts up service
```

You will need to agree the first time you trigger the script to allow it to access Finder.  Thereafter, it should behave as expected.

If the service fails to do anything of note, check out /var/log/sleep.log for potential errors.
