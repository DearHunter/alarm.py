alarm.py
========

Music Player Daemon Alarm written in Python, Raspberry Pi GPIO Button for controlling MPD on headless server
Uses mpd and mpc to play a random playlist, install these dependencies. 

### mpd_alarm.py Setup: Add this python script to a cron with your desired start time, path can be anywhere
crontab -e
Ex: "35 6 * * 1-5 /home/pi/.mpd/alarm.py To start at 6:35AM M-F"
Change varibles based on your directory structure and desired increments

### Add buttonPressGPIO.py to startup via /etc/rc.local
Some sources suggest adding to rc.local isn't a best practice.  I'm looking into daemonizing the process
python /home/pi/.mpd/button_press_GPIO.py >> /home/pi/.mpd/button.log 2>&1 &

Button wiriting: Bottom Left GND, Top Right Pin 23 and 10k resistor, 10k Resistor goes inbetween 3.3V and tied with 23
