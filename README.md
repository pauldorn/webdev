# Dockerized Web IDEs

# Always current webstorm and cllion in Docker Container

# What does it do?
Runs Webstorm or CLion (JetBrains) in a docker container.

# Where do I start?
Clone the repo and then run init.sh from inside the working directory.

# What will happen?
The init script will:
  1. Get the latest version from the jetbrains website and install it in a docker container.
  2. Create desktop shortcuts that will start your shiny new docker container sharing your X11 session with it.
  
# What Next?
Double click your nice new desktop icon.  Webstorm or CLion should ask you to provide license details.
If you started your container using the desktop icon it should remember those settings for you on the next startup.

# What can go wrong?
You may have to give your container access to XWindows using the xhost command (caveat emptor).
You may have to create the hidden directories that CLion and WebStorm use to save settings.
You may have to adjust the desktop icon settings to reflect your working directory preferences.


