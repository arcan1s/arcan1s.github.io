---
permalink: projects/awesome-widgets
hastr: true
layout: project
title: Awesome Widgets
short: awesome-widgets
tags: python, kde, qt, linux, system, awesome
hasgui: true
hasdocs: false
developers:
    - Evgeniy Alekseev
    - Ernesto Avilés Vzqz (Spanish translation)
    - Mermouy (French translation)
    - underr (Brazillian Portuguese translation)
    - Виктор Слободян (Ukrainian translation)
    - Lemueler (Chinese translation)
    - Heimen Stoffels (Dutch translation)
    - Mariusz Kocoń (Polish translation)
license: GPLv3
links:
    - Plasmoid page on <a href="//kde-look.org/content/show.php/Awesome+Widgets?content=157124" title="kde-look">kde-look.org</a>
    - DataEngine page on <a href="//kde-look.org/content/show.php/Extended+Systemmonitor+DataEngine?content=158773" title="kde-look">kde-look.org</a>
    - Archlinux <a href="//aur.archlinux.org/packages/kdeplasma-applets-awesome-widgets" title="AUR">AUR package</a>
    - <a href="//software.opensuse.org/package/plasma5-awesome-widgets" title="openSUSE">openSUSE package</a> (thanks to Kott)
    - <a href="//github.com/arcan1s/awesome-widgets/releases" title="Ubuntu">Ubuntu package</a>
    - <a href="/en/2014/09/04/migration-to-v2/" title="Migration">Migration to version 2.0</a>
    - <a href="/en/2014/12/19/aw-v21-bells-and-whistles/" title="ExtItems">Extensions</a>
    - <a href="/en/2016/06/05/aw-formatters-and-macros/" title="Formatters and macros">Formatters and macros</a>
---
<!-- info block -->

A collection of minimalistic easily configurable Plasmoids written on `C++/Qt`, which look like widgets in [Awesome WM](//awesome.naquadah.org/ "Awesome Homepage"). Also it provides additional system [DataEngine](//techbase.kde.org/Development/Tutorials/Plasma/DataEngines "Developers tutorial").

<!--more-->

**NOTE:** [LOOKING FOR TRANSLATORS!](//github.com/arcan1s/awesome-widgets/issues/14
"Ticket")

**PLASMA 5 COMPATIBLE!**

### <a href="#devel" class="anchor" id="devel"><span class="octicon octicon-link"></span></a>Developers and contributors

{% for devel in page.developers %}
* {{ devel }}{% endfor %}

Special thanks:

* [<img src="/resources/logo_CLion.svg" alt="CLion" style="width: 100px;"/>](//www.jetbrains.com/clion/)
* [Yahoo! Finance](//finance.yahoo.com/)
* [Yahoo! Weather](/weather.yahoo.com/)
* [OpenWeatherMap](//openweathermap.org/)

### <a href="#license" class="anchor" id="license"><span class="octicon octicon-link"></span></a>License

* {{ page.license }}

### <a href="#changelog" class="anchor" id="changelog"><span class="octicon octicon-link"></span></a>Changelog

[CHANGELOG](//github.com/arcan1s/awesome-widgets/blob/master/CHANGELOG "GitHub")

<!-- end of info block -->

<!-- install block -->
## <a href="#install" class="anchor" id="install"><span class="octicon octicon-link"></span></a>Installation

### <a href="#instruction" class="anchor" id="instruction"><span class="octicon octicon-link"></span></a>Instruction

* Download an [archive](//github.com/arcan1s/awesome-widgets/releases "GitHub") with latest version of source files.
* Extract it and install:

    ```bash
    cd /where/is/applet/
    cmake -B build -S sources -DCMAKE_BUILD_TYPE=Release
    cmake --build build
    cmake --install build
    ```

### <a href="#dependencies" class="anchor" id="dependencies"><span class="octicon octicon-link"></span></a>Dependencies

I want note that all were tested on latest version of dependencies.

* plasma-workspace
* cmake *(make)*
* extra-cmake-modules *(make)*
* one of supported music player *(optional, for music player monitor)*
* udev *(optional, GPU features)*
* wireless_tools *(optional, WiFi information)*

<!-- end of install block -->

<!-- howto block -->
## <a href="#howto" class="anchor" id="howto"><span class="octicon octicon-link"></span></a>How to use

Open your Plasma widgets and select `Awesome Widget`.

### <a href="#tips" class="anchor" id="tips"><span class="octicon octicon-link"></span></a>Tips & tricks

You may use different colours inside. Just put label text into html code. See [issue](//github.com/arcan1s/awesome-widgets/issues/9 "GitHub") for more details.

<!-- end of howto block -->

<!-- config block -->
## <a href="#config" class="anchor" id="config"><span class="octicon octicon-link"></span></a>Configuration

### <a href="#deconf" class="anchor" id="deconf"><span class="octicon octicon-link"></span></a>DataEngine configuration

You may edit DataEngine configuration. It is `/etc/xdg/plasma-dataengine-extsysmon.conf`
and `$HOME/.config/plasma-dataengine-extsysmon.conf`. Uncomment required line and
edit it.

### <a href="#deoptions" class="anchor" id="deoptions"><span class="octicon octicon-link"></span></a>DataEngine options

|          |           |
|----------|-----------|
| ACPIPATH | Path to ACPI devices. Default is `/sys/class/power_supply/`. |
| MPDADDRESS | MPD host address. Default is `localhost`. |
| MPDPORT | MPD host port. Default is `6600`. |
| PLAYER | Set music player. Supported players are mpd and MPRIS/DBus supported. `disable` will disable this monitor. |
| PLAYERSYMBOLS | Select symbols count for dynamic player tags. Default is `10`. |

### <a href="#widconf" class="anchor" id="widconf"><span class="octicon octicon-link"></span></a>Widget configuration

To edit output you need open Settings window and specify output format. HTML tags work as expected.

Available flags are in the table below.

**NOTE** The numbering of all arrays in variables starts at 0.

| Tag | Description | Since |
|-----|-------------|-------|
| `$time` | Time in default format. For example, `fri Nov 6 04:48:01 2013`. | 1.5.1 |
| `$isotime` | Time in ISO format. | 1.5.2 |
| `$shorttime` | Time in short locale format. | 1.5.2 |
| `$longtime` | Time in long locale format. | 1.5.2 |
| `$ctime` | Will enable custom time format. | 2.0.0 |
| `$tstime` | Curent timestamp | 3.1.2 |
| `$uptime` | System uptime, `---d--h--m`. ||
| `$cuptime` | Will enable custom uptime format. | 2.0.0 |
| `$la1` | Load average over 1 min, `-----`. | 2.4.0 |
| `$la5` | Load average over 5 min, `-----`. | 2.4.0 |
| `$la15` | Load average over 15 min, `-----`. | 2.4.0 |
| `$cpu` | Total load CPU, %, `-----`. ||
| `$cpuN` | Load CPU for core N, %, `-----`. | 1.7.0 |
| `$cpucl` | Average CPU clock, MHz, `----`. | 1.1.2 |
| `$cpuclN` | CPU clock for core N, MHz, `----`. | 1.7.0 |
| `$tempN` | Temperature for device N, `----`. For example, `$temp0`. ||
| `$gpu` | GPU usage, %, `-----`. Requies `udev` to be installed. | 1.3.2 |
| `$gpuN` | GPU usage for device N, %, `-----`. For example, `$gpu0`. Requies `udev` to be installed. | 4.0.0 |
| `$gputempN` | GPU temperature for device N, `----`. For example, `$gputemp0`. Requies `udev` to be installed. | 4.0.0 |
| `$mem` | Memory usage, %, `-----`. ||
| `$memmb` | Memory usage, MB, `-----`. | 1.1.1 |
| `$memgb` | Memory usage, GB, `----`. | 1.7.3 |
| `$memfreemb` | Free memory, MB, `-----`. | 2.0.0 |
| `$memfreegb` | Free memory, GB, `----`. | 2.0.0 |
| `$memtotmb` | RAM, MB, `-----`. | 1.10.0 |
| `$memtotgb` | RAM, GB, `----`. | 1.10.0 |
| `$memusedmb` | Used and cached memory, MB, `-----`. | 2.0.0 |
| `$memusedgb` | Used and cached memory, GB, `----`. | 2.0.0 |
| `$swap` | Swap usage, %, `-----`. ||
| `$swapmb` | Swap usage, MB, `-----`. | 1.1.1 |
| `$swapgb` | Swap usage, GB, `----`. | 1.7.3 |
| `$swapfreemb` | Free swap, MB, `-----`. | 2.0.0 |
| `$swapfreegb` | Free swap, GB, `----`. | 2.0.0 |
| `$swaptotmb` | Swap, MB, `-----`. | 1.10.0 |
| `$swaptotgb` | Swap, GB, `----`. | 1.10.0 |
| `$hddN` | Usage for mount point N, %, `-----`. For example `$hdd0`. | 1.3.2 |
| `$hddmbN` | Usage for mount point N, MB, `-----`. For example `$hddmb0`. | 1.8.0 |
| `$hddgbN` | Usage for mount point N, GB, `-----`. For example `$hddgb0`. | 1.8.0 |
| `$hddfreembN` | Free space for mount point N, MB, `-----`. For example `$hddfreemb0`. | 2.0.0 |
| `$hddfreegbN` | Free space for mount point N, GB, `-----`. For example `$hddfreegb0`. | 2.0.0 |
| `$hddtotmbN` | Total size of mount point N, MB, `-----`. For example `$hddtotmb0`. | 1.10.0 |
| `$hddtotgbN` | Total size of mount point N, GB, `-----`. For example `$hddtotgb0`. | 1.10.0 |
| `$hddrN` | Read speed of disk N, KB/s, `-----`. For example `$hddr0`. | 1.9.0 |
| `$hddwN` | Write speed of disk N, KB/s, `-----`. For example `$hddw0`. | 1.9.0 |
| `$down` | Download speed for active device, KB/s or MB/s, `----`. | 1.7.0 |
| `$downkb` | Download speed for active device, KB/s, `----`. | 3.0.0 |
| `$downunits` | Download speed units for active device, `----`. | 3.0.0 |
| `$downtotal` | Total recieved for active device, MB, `----`. | 3.1.2 |
| `$downtotalkb` | Total recieved for active device, KB, `----`. | 3.1.2 |
| `$downN` | Download speed for device N, KB/s or MB/s, `----`. | 2.2.0 |
| `$downkbN` | Download speed for device N, KB/s, `----`. | 3.0.0 |
| `$downunitsN` | Download speed units for device N, `----`. | 3.0.0 |
| `$downtotalN` | Total recieved for device N, MB, `----`. | 3.1.2 |
| `$downtotalkbN` | Total recieved for device N, KB, `----`. | 3.1.2 |
| `$up` | Upload speed for active device, KB/s or MB/s, `----`. | 1.7.0 |
| `$upkb` | Upload speed for active device, KB/s, `----`. | 3.0.0 |
| `$upunits` | Upload speed units for active device, `----`. | 3.0.0 |
| `$uptotal` | Total transmitted for active device, MB, `----`. | 3.1.2 |
| `$uptotalkb` | Total transmitted for active device, KB, `----`. | 3.1.2 |
| `$upN` | Upload speed for device N, KB/s or MB/s, `----`. | 2.2.0 |
| `$upkbN` | Upload speed for device N, KB/s, `----`. | 3.0.0 |
| `$upunitsN` | Upload speed units for device N, `----`. | 3.0.0 |
| `$uptotalN` | Total transmitted for device N, MB, `----`. | 3.1.2 |
| `$uptotalkbN` | Total transmitted for device N, KB, `----`. | 3.1.2 |
| `$netdev` | Current network device. | 1.1.1 |
| `$bat` | Average battery charge, %, `---`. ||
| `$batN` | Battery N charge, %, `---`. For example `$bat0`. | 2.0.3 |
| `$batleft` | Battery discharge time, s, `---`. | 3.4.2 |
| `$batleftN` | Battery N discharge time, s, `---`. For example `$batleft0`. | 3.4.2 |
| `$batnow` | Battery current capacity, `---`. | 3.4.2 |
| `$batnowN` | Battery N current capacity, `---`. For example `$batnow0`. | 3.4.2 |
| `$batrate` | Battery discharge rate, 1/s, `-----`. | 3.4.2 |
| `$batrateN` | Battery N discharge rate, 1/s, `-----`. For example `$batrate0`. | 3.4.2 |
| `$battotal` | Battery total capacity, `---`. | 3.4.2 |
| `$battotalN` | Battery N total capacity, `---`. For example `$battotal0`. | 3.4.2 |
| `$ac` | Status of AC device. Returns `(*)` if AC device is online or `( )` if offline. ||
| `$album` | Current song album. One of supported music players must be installed. | 1.5.3 |
| `$dalbum` | Current song album with fixed symbols count shown as a running line. | 3.0.0 |
| `$salbum` | Current song album with fixed symbols count shown with three dots at the end. | 3.0.0 |
| `$artist` | Current song artist. One of supported music players must be installed. | 1.5.0 |
| `$dartist` | Current song artist with fixed symbols count shown as a running line. | 3.0.0 |
| `$sartist` | Current song artist with fixed symbols count shown with three dots at the end. | 3.0.0 |
| `$duration` | Current song duration. One of supported music players must be installed. | 2.0.0 |
| `$progress` | Current song progress. One of supported music players must be installed. | 1.5.3 |
| `$title` | Current song title. One of supported music players must be installed. | 1.5.0 |
| `$dtitle` | Current song title with fixed symbols count shown as a running line. | 3.0.0 |
| `$stitle` | Current song title with fixed symbols count shown with three dots at the end. | 3.0.0 |
| `$ps` | List of running processes comma separated. | 1.8.0 |
| `$pscount` | Number of running processes. | 1.8.0 |
| `$pstotal` | Total number of processes. | 1.8.0 |
| `$pkgcountN` | Number of packages, which available to upgrade for command N. | 1.8.0 |
| `$responseN` | Web response for url N. | 3.3.0 |
| `$customN` | Get output from custom command N. For example `$custom0`. | 1.9.0 |
| `$desktop` | Name of the current desktop. | 2.0.0 |
| `$ndesktop` | Number of the current desktop. | 2.0.0 |
| `$tdesktops` | Total number of desktops. | 2.0.0 |
| `$askN` | Get ask for ticker N. For example `$ask0`. | 2.2.2 |
| `$askchgN` | Get absolute ask change for ticker N. For example `$askchg0`. | 2.2.2 |
| `$percaskchgN` | Get ask change for ticker N, %. For example `$percaskchg0`. | 2.2.2 |
| `$bidN` | Get bid for ticker N. For example `$bid0`. | 2.2.2 |
| `$bidchgN` | Get absolute bid change for ticker N, %. For example `$bidchg0`. | 2.2.2 |
| `$percbidchgN` | Get bid change for ticker N. For example `$percbidchg0`. | 2.2.2 |
| `$priceN` | Get price for ticker N. For example `$price0`. | 2.2.2 |
| `$pricechgN` | Get absolute price change for ticker N. For example `$pricechg0`. | 2.2.2 |
| `$percaskchgN` | Get price change for ticker N, %. For example `$percpricechg0`. | 2.2.2 |
| `$weatherIdN` | Numerical weather ID. For example `$weatherId0`. | 2.4.0 |
| `$weatherN` | Weather status. For example `$weather0`. | 2.4.0 |
| `$humidityN` | Humidity, %, `---`. For example `$humidity0`. | 2.4.0 |
| `$pressureN` | Pressure, bars, `-----`. For example `$pressure0`. | 2.4.0 |
| `$temperatureN` | Temperature, `-----`. For example `$temperature0`. | 2.4.0 |
| `$brightness` | Screen brightness, %, `---` | 3.4.2 |
| `$volume` | System volume, %, `---`. | 3.4.2 |
| `$ssid` | Current WiFi ssid. `wireless_tools` must be installed. | 4.0.0 |

### <a href="#lambda" class="anchor" id="lambda"><span class="octicon octicon-link"></span></a>Lambda and template functions

Since version 3.0.0 the main widget supports lambda functions, which are calculated at runtime. It may be declared by using `{% raw %}${{{% endraw %} {% raw %}}}{% endraw %}` construction:

```javascript
{% raw %}${{{% endraw %}
function three()
{
    return 1+2;
}
three()
{% raw %}}}{% endraw %}
```

A functions inside will be interpreted as JavaScript ones, any variables from main body is supported, thus the following function:

```javascript
{% raw %}${{{% endraw %}
function colorCpu()
{
    if ($cpu > 90.0)
        return "<span style=\"color:#ff0000;\">$cpu</span>"
    else
        return "$cpu"
}
colorCpu()
{% raw %}}}{% endraw %}
```

will show `$cpu` value in red if it is more than 90.0, otherwise it will be shown in default colour. Any calculations are also supported:

```javascript
{% raw %}${{{% endraw %}
$down - $up
{% raw %}}}{% endraw %}
```

will show difference between download and upload speed. Another feature provided by lambda functions is `$this` value which returns the last value of the lambda function. Here is a little more complicated example which will show running line "Artist - Title" with length less or equal than 20 symbols:

```javascript
{% raw %}${{{% endraw %}
function runningLine() {
    var current = "$artist - $title";
    var index = current.indexOf("$this");
    if (("$this" == "") || ((index + 20 + 1) > current.length))
        return current.substring(0, 20);
    else
        return current.substring(index + 1, index + 20 + 1);
}
runningLine()
{% raw %}}}{% endraw %}
```

Thus this feature may be used for example to show any custom values which will be calculated in runtime and to show different information depending on some conditions. But please keep in mind that such runtime calculation may increase CPU load.

Another feature which has been introduced with 3.1.0 is templates. It works in the same way as lambda functions, but they are calculated only once (at the start), e.g.:

```javascript
{% raw %}$template{{{% endraw %}
function three()
{
    return 1+2;
}
three()
{% raw %}}}{% endraw %}
```

will always show `3` and will not be calculated each time.

### <a href="#functions" class="anchor" id="functions"><span class="octicon octicon-link"></span></a>Special functions

To allow some features with lambdas and templates several internal functions have been introduced with 3.1.0. They have the same syntax: `$aw_function<args>{% raw %}{{{% endraw %}body{% raw %}}}{% endraw %}`, where args may be optional. If there are several args they should be comma separated. If you want to pass comma as arg use `$,`. If you want to use double brackets inside body screen them by using `$`, e.g. `${`. Functions will be called once and before any actions.

| Function | Description | Args | Body |
|----------|-------------|------|------|
| `aw_all` | was introduced for debug purposes, return all keys by regexp in pretty format | separator | regexp for search |
| `aw_count` | return count of keys by given regexp | (none) | regexp for search |
| `aw_keys` | return keys by given regexp joined by separator | separator | regexp for search |
| `aw_names` | return key names (i.e. without `$`) by given regexp joined by separator | separator | regexp for search |
| `aw_macro` | define user macro | macro name, macro arguments if any | macro body |
| `aw_macro_*` | (* is macro name) call of user defined macro | macro arguments in the same order | ignored |

### <a href="#advanced" class="anchor" id="advanced"><span class="octicon octicon-link"></span></a>Advanced settings

**Enable background:** Uncheck to disable default background and set transparent one. Default is `true`.

**Translate strings:** Translate strings tags. Default is `true`.

**Wrap new lines:** Replace `\n` to `&#60;br&#62;`. Default is `false`.

**Word wrap:** Enable word wrap. Default is `false`.

**Enable popup:** Uncheck box if you do not want popup messages on system events. Default is `true`.

**Check updates:** Check updates on load. Default is `true`.

**Optimize subscription:** Optimize work with DataEngines. Probably you don't want change this option despite the fact that one feature will not be available. Default is `true`.

**Widget height:** Disable automatic widget height definition and set it to this value. Default is `0` (auto).

**Widget width:** Disable automatic widget width definition and set it to this value. Default is `0` (auto).

**Update interval:** Widget update interval. Default is `1000`.

**Temperature units:** Select units for temperature. Available units are Celsius, Farenheit, Kelvin, Reaumur, cm^-1, kJ/mol, kcal/mol.

**Custom time format:**

|         |                         |
|---------|-------------------------|
| `$dddd` | Weekday in long format. |
| `$ddd` | Weekday in short format. |
| `$dd` | Day. |
| `$d` | Day without zero. |
| `$MMMM` | Month in long format. |
| `$MMM` | Month in short format. |
| `$MM` | Month. |
| `$M` | Month without zero. |
| `$yyyy` | Year. |
| `$yy` | Year in short format. |
| `$hh` | Hours. |
| `$h` | Hours without zero. |
| `$HH` | Hours in 24-hours format. |
| `$H` | Hours in 24-hours format without zero. |
| `$mm` | Minutes. |
| `$m` | Minutes without zero. |
| `$ss` | Seconds. |
| `$s` | Seconds without zero. |
| `$t` | Timezone name. |
| `$a`/`$ap` | am or pm. |
| `$A`/`$AP` | AM or PM. |

**Custom uptime format:**

|       |              |
|-------|--------------|
| `$dd` | Uptime days. |
| `$d` | Uptime days without zero. |
| `$hh` | Uptime hours. |
| `$h` | Uptime hours without zero. |
| `$mm` | Uptime minutes. |
| `$m` | Uptime minutes without zero. |

**AC online tag:** Line which will be shown when AC is online. Default is `(*)`.

**AC offline tag:** Line which will be shown when AC is offline. Default is `( )`.

**History count:** Total count of stored configurations localy.

### <a href="#tooltips" class="anchor" id="tooltips"><span class="octicon octicon-link"></span></a>Tooltips

Since version 1.7.0 CPU, CPU clock, memory, swap, network and battery support graphical tooltip. To enable them just select required fields. The number of stored values can be set in the tab. Colours of the graphs are configurable too.

### <a href="#deguiconf" class="anchor" id="deguiconf"><span class="octicon octicon-link"></span></a>DataEngine settings

**ACPI path:** Path to ACPI devices. The file `/sys/class/power_supply/`.

**Player symbol count:** Symbol count for dynamic player tags.

**Music player:** Select one of supported music players for player label.

**MPRIS:** Select MPRIS player name. `auto` will enable auto selection. Default is `auto`.

**MPD address:** Address of MPD server. Default is `localhost`.

**MPD port:** Port of MPD server. Default is `6600`.

### <a href="#desktoppanel" class="anchor" id="desktoppanel"><span class="octicon octicon-link"></span></a>Desktop Panel

Since version 1.11.0 it provides a minimalistic panel to control destops. And yes, it looks like the same panel in Awesome.

### <a href="#dpconf" class="anchor" id="dpconf"><span class="octicon octicon-link"></span></a>Desktop panel configuration

**Enable background:** Uncheck to disable default background and set transparent one. Default is `true`.

**Vertical layout:** Use vertical layout instead of horizontal one. Default is `false`.

**Widget height:** Disable automatic widget height definition and set it to this value. Default is `0` (auto).

**Widget width:** Disable automatic widget width definition and set it to this value. Default is `0` (auto).

**Mark:** Type symbol (or string) which will be shown if this desktop is active now.

**Tooltip type:** Select tooltip type. Default is `contours`.

**Tooltip width:** Using tooltip width in px. Default is `200px`.

**Color of tooltip:** Colour which is used in some tooltip types. Default is `#ffffff`.

**Pattern tags**

|         |         |
|---------|---------|
| `$mark` | Show mark if this desktop is active. Shows spaces in other way. |
| `$name` | Name of the desktop. |
| `$number` | Number of the desktop. |
| `$total` | Total number of desktops. |

<!-- end of config block -->

<!-- gui block -->
## <a href="#gui" class="anchor" id="gui"><span class="octicon octicon-link"></span></a>Graphical user interface

## <a href="#screenshots" class="anchor" id="screenshots"><span class="octicon octicon-link"></span></a>Screenshots

<div class="thumbnails">
  {% assign scrdesc = "Widget (clickable)" %}
  {% assign scrname = "awesomewidgets_widget" %}
  {% include prj_scr.html %}
  {% assign scrdesc = "Configuration window" %}
  {% assign scrname = "awesomewidgets_config_01" %}
  {% include prj_scr.html %}
  {% assign scrdesc = "Configuration window" %}
  {% assign scrname = "awesomewidgets_config_02" %}
  {% include prj_scr.html %}
  {% assign scrdesc = "Configuration window" %}
  {% assign scrname = "awesomewidgets_config_03" %}
  {% include prj_scr.html %}
  {% assign scrdesc = "Configuration window" %}
  {% assign scrname = "awesomewidgets_config_04" %}
  {% include prj_scr.html %}
  {% assign scrdesc = "Configuration window" %}
  {% assign scrname = "awesomewidgets_config_05" %}
  {% include prj_scr.html %}
  {% assign scrdesc = "Tooltips" %}
  {% assign scrname = "awesomewidgets_tooltips" %}
  {% include prj_scr.html %}
</div>
