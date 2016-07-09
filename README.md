##i3wm config на основе Archlinux
Установка модифицированного [i3-gaps-git](https://github.com/Airblader/i3/tree/gaps), панели [i3blocks-gaps-git ](https://github.com/Airblader/i3blocks-gaps), красивого меню [rofi-git](https://davedavenport.github.io/rofi/), модифицированного dmenu [j4-dmenu-desktop](https://github.com/enkore/j4-dmenu-desktop), катологизированное меню [morc_menu](https://github.com/Boruch-Baum/morc_menu)
```
yaourt -Sy --noconfirm i3-gaps-git rofi-git j4-dmenu-desktop rofi-git j4-dmenu-desktop
 
cd /tmp
git clone https://github.com/Boruch-Baum/morc_menu.git
cd morc_menu
sudo make install
```
Шрифты
```
ttf-weather-icons ttf-font-awesome ttf-ubuntu-font-family
```
Индикатор раскладки sbxkb, установка обоев nitrogen, компизный менеджер compton, менеджер питания xfce4-power-manager, минималистичный демон системных уведомлений dunst, изменение цветовой температуры дисплея от времени суток redshift, bluetooth апплет blueman-applet, автомотическое монтирование съемных носителей udiskie, управление медиаплеерами при помощи горячих клавиш playerctl
```
yaourt -S --noconfirm sbxkb nitrogen compton xfce4-power-manager dunst redshift blueman-applet udiskie scrot playerctl
```
Другие приложения, задействованные в данных скриптах
[rxvt-unicode](https://wiki.archlinux.org/index.php/Rxvt-unicode) [terminator](https://wiki.archlinux.org/index.php/Terminator) [alsa](https://wiki.archlinux.org/index.php/Advanced_Linux_Sound_Architecture) [pulseaudio](https://wiki.archlinux.org/index.php/PulseAudio) [google-chrome](https://aur.archlinux.org/packages/google-chrome) [thunderbird](https://wiki.archlinux.org/index.php/Thunderbird) [cheese](https://www.archlinux.org/packages/?sort=&q=cheese&maintainer=&flagged=) [gnome-calculator](https://www.archlinux.org/packages/?sort=&q=gnome-calculator&maintainer=&flagged=) [gnome-calendar](https://www.archlinux.org/packages/?sort=&q=gnome-calendar&maintainer=&flagged=) [pycharm](https://aur.archlinux.org/packages/pycharm-community) [audacious](https://wiki.archlinux.org/index.php/Audacious) [libreoffice](https://wiki.archlinux.org/index.php/LibreOffice) [wps-office](https://aur.archlinux.org/packages/wps-office/) [viber](https://aur.archlinux.org/packages/wps-office/) [nm-applet](https://wiki.archlinux.org/index.php/NetworkManager#Other_desktops_and_window_managers) [oblogout](https://wiki.archlinux.org/index.php/Oblogout) [wego](https://aur.archlinux.org/packages/wego-git/)
 
###Установка и настройка конфигов
```
cd /tmp
https://github.com/dvino/i3wm.git
cp i3wm/i3 ~/.config
```
####mail 
Для работы виджета проверки почты необходимо внести свои данные в скрипт **.config/i3/scrypts/mail** заменить адрес сервера **imap.EXAMPLE.COM** и логин с паролем **USERNAME, PASSWORD**
 
####vk
Для виджета проверки входящий сообщений vk.com необходимо [установить модуль](https://aur.archlinux.org/packages/python-pip-git/) vk\_api для python
```
pip install vk_api
```
В сам скрипт **.config/i3/scrypts/vk** внести свои данные: вписать логин с паролем **USERNAME, PASSWORD**, а так же **ACCESS TOKEN**, который можно получить следующим образом:
Завести себе [id приложения](https://new.vk.com/editapp?act=create). Тип приложения должен обязательно быть **standalone**. и заменяем в ссылке следующего вида NNNNNNNN на ID вашего приложения
```
https://oauth.vk.com/authorize?client\_id=NNNNNNN&display=page&redirect\_uri=https://oauth.vk.com/blank.html&scope=messages&response\_type=token&v=5.52
```
Копируем ее в браузер. Из ответной ссылки после авторизации и подтверждения доступа берем значение **access token**
 
####weather 
Для работы виждета погоды, а так же для погодного скрипта [wego](https://github.com/schachmat/wego) необходимо зарегистрировать акаунт https://github.com/schachmat/wego. Далее внесите значения своего api и местоположения в **.config/i3/scrypts/weather_temp** 

###Обратная связь
[vk.com](https://new.vk.com/danil_vinokurov); [email](danil@vinokurov.tk)
