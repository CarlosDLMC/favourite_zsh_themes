Para instalar zsh:
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

Para que el tema de agnoster funcione bien, hay que tener una fuente compatible. Este problema se soluciona simplemente con:

sudo apt-get install fonts-powerline

Además, para que la terminal se vea bonita:

Color de texto: #FFFFFF
Color de fondo: #2C2D2E

Además, el plugin que usamos es zsh-autosuggestions
Para instalarlo:
1-Vamos a la carpeta ~/.oh-my-zsh/custom/plugins
2-En ella clonamos https://github.com/zsh-users/zsh-autosuggestions.git
3-Abrimos ~/.zshrc 
4-Añadimos zsh-autosuggestions en la tupla que se llama plugins (SIN COMAS).
5-Reiniciamos terminal

To view available speed governors use this command:
cat /sys/devices/system/cpu/cpu0/cpufreq/scaling_available_governors

If you do have more than one governor you can check what is currently in use with this command:
cat /sys/devices/system/cpu/cpu0/cpufreq/scaling_governor

To change your processor to performance mode use:
echo performance | sudo tee /sys/devices/system/cpu/cpu*/cpufreq/scaling_governor

Si el pc laggea cuando está cargando:
To make this a permanent solution, create/edit /etc/modprobe.d/local.conf to add the following line:

options drm_kms_helper poll=N

Also try this if the laptop runs slow when plugged in:
Terminal

gksu gedit /etc/default/grub

The option you want to edit is:

GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"
GRUB_CMDLINE_LINUX=""

You can either add drm_kms_helper.poll=N after the splash parameter in the first line or add inside the quoted part in the second part.
