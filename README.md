# Requirements
- Python3.8 or greater
- Java 11

# Instructions
1. Create a Python virtual environment with virtualenv
    1. `python3 -m pip install virtualenv`
    2. `python3 -m virtualenv redenv`
2. Within that virtual environment, pip install the Red-DiscordBot package
    1. `source redenv/bin/activate`
    2. `python -m pip install -U pip setuptools wheel`
    3. `python -m pip install -U Red-DiscordBot`
    - NOTE: This next step is needed to use the audio cog (play music in a voice channel).
    4. `python -m pip install -U apsw`
3. Run the redbot setup utility
    - `redbot-setup`
4. Start your rebot instance
    - `redbot <change_this_name>`
5. Open the service file with a text editor and change the path of the executable to match your virtual environment.
    - `ExecStart=<change_this_path>/redenv/bin/python -O -m redbot %I --no-prompt`
6. Copy the redbot.service file into /etc/system/systemd
    - NOTE: This step requires sudo permissions.
    - `sudo cp redbot@.service /etc/system/systemd`
7. Restart the systemd daemon and start your service.
    - NOTE: This step requires sudo permissions.
    1. `sudo systemctl daemon-reload`
    2. `sudo systemctl start redbot@<instance_name>`
8. Check the status of the service.
    - NOTE: This step requires sudo permissions.
    - `sudo systemctl status redbot@<instance_name>`
9. Once you verify that your service started without any errors, enable it to run on boot up.
    - NOTE: This step requries sudo permissions.
    - `sudo systemctl enable redbot@<instance_name>`
