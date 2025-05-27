# Fil- og mappehåndtering
ls                     # Vis filer og mapper i den nuværende mappe
ls -l                  # Vis detaljeret listevisning
ls -a                  # Vis skjulte filer
cd `<mappe>`           # Skift til en anden mappe
cd ..                  # Gå én mappe op
cd ~                   # Gå til hjemmemappen
pwd                    # Vis den nuværende sti
mkdir `<mappe>`        # Opret en ny mappe
rm `<fil>`             # Slet en fil
rm -r `<mappe>`        # Slet en mappe og dens indhold
mv `<fil>` `<sti>/`    # Flyt eller omdøb en fil
cp `<fil>` `<sti>/`    # Kopier en fil til en anden mappe
cp -r `<mappe>` `<sti>/`  # Kopier en mappe rekursivt

# C++ Kompilering og CMake
g++ `<fil.cpp>` -o `<output>`        # Kompiler en enkelt C++-fil
g++ *.cpp -o `<output>`              # Kompiler alle C++-filer i mappen
g++ -Wall -Wextra `<fil.cpp>` -o `<output>`  # Aktiver advarsler

# CMake byggeprocessen
cmake ..                        # Generér Makefile (fra en build-mappe)
cmake --build .                 # Byg projektet (efter cmake ..)
cmake -DCMAKE_BUILD_TYPE=Debug ..  # Konfigurer CMake i debug-mode

# Kørsel af programmer
./`<output>`                    # Kør det kompilerede program
./a.out                         # Standard outputfil for g++

# Pakkehåndtering (Debian/Ubuntu)
sudo apt update                 # Opdater pakkelisten
sudo apt upgrade                # Opgrader installerede pakker
sudo apt install `<pakke>`       # Installer en pakke
sudo apt remove `<pakke>`        # Fjern en pakke

# System og information
uname -a                        # Vis systeminformation
df -h                           # Vis diskplads
du -sh `<mappe>`                # Vis mappe-størrelse
htop                            # Interaktiv procesmonitor (kræver installation)
top                             # Vis kørende processer
ps aux                          # Vis alle processer
kill `<PID>`                    # Dræb en proces med PID
killall `<navn>`                # Dræb alle processer med et givet navn

# Filvisning og redigering
cat `<fil>`                     # Vis filindhold
less `<fil>`                    # Vis en fil med scroll-mulighed
nano `<fil>`                    # Rediger en fil i Nano-editoren
vim `<fil>`                     # Rediger en fil i Vim-editoren

# Netværk
ping `<adresse>`                 # Send ping til en server
curl `<URL>`                     # Hent indhold fra en webside
wget `<URL>`                     # Download en fil fra internettet
netstat -tulnp                   # Vis aktive netværksforbindelser
ip a                             # Vis netværkskonfiguration

# Filrettigheder
chmod +x `<fil>`                  # Gør en fil eksekverbar
chown `<bruger>`:`<gruppe>` `<fil>`  # Skift ejer af en fil
chmod 644 `<fil>`                  # Ændr filens læse- og skrive-rettigheder

# Versionsstyring med Git
git init                         # Initialiser et Git-repository
git status                       # Se ændringer i working directory
git add `<fil>`                   # Tilføj en fil til staging
git commit -m "besked"           # Commit ændringer
git clone `<repo-URL>`           # Klon et repository
git pull                         # Hent og merge ændringer fra remote
git push                         # Skub ændringer til remote repository

# Baggrundsprocesser
./`<program>` &                  # Kør program i baggrunden
jobs                             # Se baggrundsprocesser
fg `%1`                          # Bring job 1 til forgrunden
bg `%1`                          # Genoptag job 1 i baggrunden
kill `%1`                        # Dræb baggrundsjob 1
nohup ./`<program>` &            # Kør program og ignorer logout

# Søgning
grep "tekst" `<fil>`              # Søg efter "tekst" i en fil
find . -name "`<filnavn>`"        # Find en fil i nuværende mappe
locate `<fil>`                    # Find en fil hurtigt (kræver databaseopdatering)
history | grep `<kommando>`        # Søg efter tidligere kommandoer

# Tidsstyring
sleep 5                          # Vent i 5 sekunder
date                             # Vis dato og tid
cal                              # Vis en kalender
uptime                           # Vis systemets oppetid

# Andre nyttige kommandoer
echo "tekst"                     # Udskriv tekst til terminalen
alias ll='ls -la'                # Opret en alias for en kommando
clear                            # Ryd terminalen
exit                             # Luk terminalen
reboot                           # Genstart systemet
shutdown now                     # Sluk systemet med det samme
zip -r `<navn.zip>` `<navn på det der zippes>`    # Zipper en mappe, hvor -r betyder recursive.

# Dagligdagskommandoer
wget <image_url> -O <save_as> # Gemme et billede
sudo apt update
sudo apt upgrade
sudo apt autoremove

# ROS
ros2 launch ur_robot_driver ur_control.launch.py ur_type:=ur5 robot_ip:=192.168.1.54
(Husk at sætte connection på PC til at være 192.168.1.55; 255.255.255.0; 1.1.1.1)
ros2 launch ur_moveit_config ur_moveit.launch.py ur_type:=ur5 launch_rviz:=true
ros2 run ur5_sem2_scripts svejse_frame 
ros2 run ur5_sem2_scripts final_main --ros-args -p camera_index:=`<insert index>`
# Pico
sudo chmod a+rw /dev/ttyACM0