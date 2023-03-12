---
description: >-
  GNU Radio is an open-source software that provides a platform for building
  software-defined radios and signal processing systems using SDR technology.
---

# 📻 gnuradio

GNU Radio is an open-source software tool that provides a platform for building software-defined radio systems. It allows users to build custom signal processing blocks and combine them to create complex radio systems for various applications such as communication, radar, and radio astronomy. GNU Radio provides a graphical user interface and a set of signal processing blocks that can be easily interconnected using a drag-and-drop interface. The tool is written in Python and C++, and it can be used on a variety of platforms including Linux, Windows, and MacOS. It also supports various hardware devices such as universal software radio peripherals (USRP), HackRF, and RTL-SDR. GNU Radio is widely used in academic research, industry, and hobbyist projects.

### Packages and Binaries:

#### gnuradio <a href="#gnuradio" id="gnuradio"></a>

GNU Radio provides signal processing blocks to implement software radios. It can be used with readily-available low-cost external RF hardware to create software-defined radios, or without hardware in a simulation-like environment. It is widely used in hobbyist, academic and commercial environments to support both wireless communications research and real-world radio systems.

GNU Radio applications are primarily written using the Python programming language, while the supplied performance-critical signal processing path is implemented in C++ using processor floating-point extensions, where available. Thus, the developer is able to implement real-time, high-throughput radio systems in a simple-to-use, rapid-application-development environment.

While not primarily a simulation tool, GNU Radio does support development of signal processing algorithms using pre-recorded or generated data, avoiding the need for actual RF hardware.

This package contains the gnuradio-companion, a graphical tool for creating signal flow graphs and generating flow-graph source code. Also included are a variety of tools and utility programs.

**Installed size:** `21.16 MB`\
**How to install:** `sudo apt install gnuradio`

<details>

<summary>Dependencies:</summary>

* gnome-terminal | x-terminal-emulator
* libboost-program-options1.74.0
* libc6
* libfmt9
* libgcc-s1
* libgmp10
* libgnuradio-analog3.10.5
* libgnuradio-audio3.10.5
* libgnuradio-blocks3.10.5
* libgnuradio-channels3.10.5
* libgnuradio-digital3.10.5
* libgnuradio-dtv3.10.5
* libgnuradio-fec3.10.5
* libgnuradio-fft3.10.5
* libgnuradio-filter3.10.5
* libgnuradio-iio3.10.5
* libgnuradio-network3.10.5
* libgnuradio-pdu3.10.5
* libgnuradio-pmt3.10.5
* libgnuradio-qtgui3.10.5
* libgnuradio-runtime3.10.5
* libgnuradio-soapy3.10.5
* libgnuradio-trellis3.10.5
* libgnuradio-uhd3.10.5
* libgnuradio-video-sdl3.10.5
* libgnuradio-vocoder3.10.5
* libgnuradio-wavelet3.10.5
* libgnuradio-zeromq3.10.5
* libjs-mathjax
* libqt5core5a
* libqt5widgets5
* libsoapysdr0.8
* libspdlog1.10-fmt9
* libstdc++6
* libuhd4.3.0
* libvolk2-bin
* libvolk2.5
* python3
* python3
* python3-click
* python3-click-plugins
* python3-gi
* python3-gi-cairo
* python3-jsonschema
* python3-lxml
* python3-mako
* python3-numpy
* python3-numpy-abi9
* python3-opengl
* python3-packaging
* python3-pygccxml
* python3-pyqt5
* python3-pyqtgraph
* python3-schema
* python3-sip
* python3-thrift
* python3-yaml
* python3-zmq

</details>

**dial\_tone**

Dial tone example

```
:~# man dial_tone
DIAL_TONE(1)                     User Commands                    DIAL_TONE(1)

NAME
       dial_tone - dial tone example

DESCRIPTION
       GnuRadio Dial Tone example

OPTIONS
       None

       Play a Dial Tone on the sound card output device.

SEE ALSO
       The  c++ gnuradio example programs are in /usr/bin. There are also many
       Python and GnuRadio  Companion  examples  in  /usr/share/gnuradio/exam-
       ples/...

       tags_demo(1)      uhd_rx_cfile(1)     uhd_rx_nogui(1)     uhd_siggen(1)
       uhd_siggen_gui(1)

DIAL_TONE 3.10.5.1                2023-02-04                      DIAL_TONE(1)
```

***

**display\_qt**

A Gnu Radio Example gr-qtgui

```
:~# man display_qt
DISPLAY_QT(1)                    User Commands                   DISPLAY_QT(1)

NAME
       display_qt - a Gnu Radio Example gr-qtgui

DESCRIPTION
       Display a GUI using QT of a sine wave in noise.

       Example  program  instantiates a GNU Radio flow graph using a sine wave
       source, a noise source, and  gr-qtgui  blocks.  This  new  (in  version
       3.7.10) example shows how to build a C++ only QT based application.

SEE ALSO
       http://gnuradio.squarespace.com/examples/tag/qt

display_qt 3.10.5.1               2023-02-04                     DISPLAY_QT(1)
```

***

**gnuradio-companion**

GNU Radio Companion (GRC) is a graphical tool for creating GNU Radio signal flowgraphs.

```
:~# gnuradio-companion -h
usage: gnuradio-companion [-h] [--log {debug,info,warning,error,critical}]
                          [flow_graphs ...]

GNU Radio Companion 3.10.5.1 This program is part of GNU Radio GRC comes with
ABSOLUTELY NO WARRANTY. This is free software, and you are welcome to
redistribute it.

positional arguments:
  flow_graphs

options:
  -h, --help            show this help message and exit
  --log {debug,info,warning,error,critical}
```

***

**gnuradio-config-info**

Show details on installed GNU radio

```
:~# gnuradio-config-info -h
Program options: gnuradio-config-info [options]:
  -h [ --help ]         print help message
  --print-all           print all information
  --prefix              print GNU Radio installation prefix
  --sysconfdir          print GNU Radio system configuration directory
  --prefsdir            print GNU Radio preferences directory
  --userprefsdir        print GNU Radio user preferences directory
  --prefs               print GNU Radio preferences
  --builddate           print GNU Radio build date (RFC2822 format)
  --enabled-components  print GNU Radio build time enabled components
  --cc                  print GNU Radio C compiler version
  --cxx                 print GNU Radio C++ compiler version
  --cflags              print GNU Radio CFLAGS
  -v [ --version ]      print GNU Radio version
  --pybind              print pybind11 version used in this build

```

***

**gr-ctrlport-monitor**

Gnuradio control port gui

```
:~# gr-ctrlport-monitor -h
usage: gr-ctrlport-monitor [-h] [host] port

GNU Radio Control Port Monitor

positional arguments:
  host        host name or IP
  port        port

options:
  -h, --help  show this help message and exit
```

***

**gr-perf-monitorx**

Gnuradio control port gui

```
:~# gr-perf-monitorx -h
usage: gr-perf-monitorx [-h] [host] port

GNU Radio Performance Monitor

positional arguments:
  host        host name or IP
  port        port

options:
  -h, --help  show this help message and exit
```

***

**gr\_filter\_design**

GUI for creating filters for GNU Radio

```
:~# gr_filter_design -h
Usage: gr_filter_design: [options] (input_filename)

Options:
  -h, --help  show this help message and exit
```

***

**gr\_modtool**

The swiss army knife of module editing

```
:~# gr_modtool --help
Usage: gr_modtool [OPTIONS] COMMAND [ARGS]...

  A tool for editing GNU Radio out-of-tree modules.

Options:
  --help  Show this message and exit.

Commands:
  add       Adds a block to the out-of-tree module.
  bind      Generate Python bindings for GR block
  disable   Disable selected block in module.
  info      Return information about a given module
  makeyaml  Generate YAML files for GRC block bindings.
  newmod    Create new empty module, use add to add blocks.
  rename    Rename a block inside a module.
  rm        Remove a block from a module.
  update    Update the grc bindings for a block

  Manipulate with GNU Radio modules source code tree. Call it without options
  to run specified command interactively
```

***

**gr\_plot**

Display time series of samples from a file

```
:~# gr_plot -h
usage: gr_plot [-h]
               [-d {complex64,float32,uint32,int32,uint16,int16,uint8,int8}]
               [-B BLOCK] [-s START] [-R SAMPLE_RATE]
               FILE [FILE ...]

Takes a GNU Radio binary file and displays the samples versus time. You can
set the block size to specify how many points to read in at a time and the
start position in the file. By default, the system assumes a sample rate of 1,
so in time, each sample is plotted versus the sample number. To set a true
time axis, set the sample rate (-R or --sample-rate) to the sample rate used
when capturing the samples.

positional arguments:
  FILE                  Input file with samples

options:
  -h, --help            show this help message and exit
  -d {complex64,float32,uint32,int32,uint16,int16,uint8,int8}, --data-type {complex64,float32,uint32,int32,uint16,int16,uint8,int8}
                        Specify the data type [default='complex64']
  -B BLOCK, --block BLOCK
                        Specify the block size [default=1000]
  -s START, --start START
                        Specify where to start in the file [default=0]
  -R SAMPLE_RATE, --sample-rate SAMPLE_RATE
                        Set the sampler rate of the data [default=1.0]
```

***

**gr\_plot\_const**

Constellation plot of I\&Q data using GNU Radio

```
:~# gr_plot_const -h
usage: gr_plot_const [-h] [-B BLOCK] [-s START] [-R SAMPLE_RATE] FILE

Takes a GNU Radio complex binary file and displays the I&Q data versus time
and the constellation plot (I vs. Q). You can set the block size to specify
how many points to read in at a time and the start position in the file. By
default, the system assumes a sample rate of 1, so in time, each sample is
plotted versus the sample number. To set a true time axis, set the sample rate
(-R or --sample-rate) to the sample rate used when capturing the samples.

positional arguments:
  FILE                  Input file with complex samples

options:
  -h, --help            show this help message and exit
  -B BLOCK, --block BLOCK
                        Specify the block size [default=1000]
  -s START, --start START
                        Specify where to start in the file [default=0]
  -R SAMPLE_RATE, --sample-rate SAMPLE_RATE
                        Set the sampler rate of the data [default=1.0]
```

***

**gr\_plot\_fft**

Frequency domain GNU Radio plotting

```
:~# gr_plot_fft -h
usage: gr_plot_fft [-h]
                   [-d {complex64,float32,uint32,int32,uint16,int16,uint8,int8}]
                   [-B BLOCK] [-s START] [-R SAMPLE_RATE]
                   FILE

Takes a GNU Radio complex binary file and displays the I&Q data versus time as
well as the frequency domain (FFT) plot. The y-axis values are plotted
assuming volts as the amplitude of the I&Q streams and converted into dBm in
the frequency domain (the 1/N power adjustment out of the FFT is performed
internally). The script plots a certain block of data at a time, specified on
the command line as -B or --block. This value defaults to 1000. The start
position in the file can be set by specifying -s or --start and defaults to 0
(the start of the file). By default, the system assumes a sample rate of 1, so
in time, each sample is plotted versus the sample number. To set a true time
and frequency axis, set the sample rate (-R or --sample-rate) to the sample
rate used when capturing the samples.

positional arguments:
  FILE                  Input file with samples

options:
  -h, --help            show this help message and exit
  -d {complex64,float32,uint32,int32,uint16,int16,uint8,int8}, --data-type {complex64,float32,uint32,int32,uint16,int16,uint8,int8}
                        Specify the data type [default='complex64']
  -B BLOCK, --block BLOCK
                        Specify the block size [default=1000]
  -s START, --start START
                        Specify where to start in the file [default=0]
  -R SAMPLE_RATE, --sample-rate SAMPLE_RATE
                        Set the sampler rate of the data [default=1.0]
```

***

**gr\_plot\_iq**

Plot complex binary I\&Q data versus time using GNU Radio

```
:~# gr_plot_iq -h
usage: gr_plot_iq [-h] [-B BLOCK] [-s START] [-R SAMPLE_RATE] FILE

Takes a GNU Radio complex binary file and displays the I&Q data versus time.
You can set the block size to specify how many points to read in at a time and
the start position in the file. By default, the system assumes a sample rate
of 1, so in time, each sample is plotted versus the sample number. To set a
true time axis, set the sample rate (-R or --sample-rate) to the sample rate
used when capturing the samples.

positional arguments:
  FILE                  Input file with complex samples

options:
  -h, --help            show this help message and exit
  -B BLOCK, --block BLOCK
                        Specify the block size [default=1000]
  -s START, --start START
                        Specify where to start in the file [default=0]
  -R SAMPLE_RATE, --sample-rate SAMPLE_RATE
                        Set the sampler rate of the data [default=1.0]
```

***

**gr\_plot\_psd**

GNU Radio power spectrum plotting

```
:~# gr_plot_psd -h
usage: gr_plot_psd [-h]
                   [-d {complex64,float32,int32,uint32,int16,uint16,int8,uint8}]
                   [-B BLOCK] [-s START] [-R SAMPLE_RATE]
                   [--psd-size PSD_SIZE] [--spec-size SPEC_SIZE] [-S]
                   FILE

Takes a GNU Radio binary file (with specified data type using --data-type) and
displays the I&Q data versus time as well as the power spectral density (PSD)
plot. The y-axis values are plotted assuming volts as the amplitude of the I&Q
streams and converted into dBm in the frequency domain (the 1/N power
adjustment out of the FFT is performed internally). The script plots a certain
block of data at a time, specified on the command line as -B or --block. The
start position in the file can be set by specifying -s or --start and defaults
to 0 (the start of the file). By default, the system assumes a sample rate of
1, so in time, each sample is plotted versus the sample number. To set a true
time and frequency axis, set the sample rate (-R or --sample-rate) to the
sample rate used when capturing the samples. Finally, the size of the FFT to
use for the PSD and spectrogram plots can be set independently with --psd-size
and --spec-size, respectively. The spectrogram plot does not display by
default and is turned on with -S or --enable-spec.

positional arguments:
  FILE                  Input file with samples

options:
  -h, --help            show this help message and exit
  -d {complex64,float32,int32,uint32,int16,uint16,int8,uint8}, --data-type {complex64,float32,int32,uint32,int16,uint16,int8,uint8}
                        Specify the data type [default='complex64']
  -B BLOCK, --block BLOCK
                        Specify the block size [default=8192]
  -s START, --start START
                        Specify where to start in the file [default=0]
  -R SAMPLE_RATE, --sample-rate SAMPLE_RATE
                        Set the sampler rate of the data [default=1.0]
  --psd-size PSD_SIZE   Set the size of the PSD FFT [default=1024]
  --spec-size SPEC_SIZE
                        Set the size of the spectrogram FFT [default=256]
  -S, --enable-spec     Turn on plotting the spectrogram [default=False]
```

***

**gr\_plot\_qt**

Plot data using Qt graphics and GNU Radio

```
:~# man gr_plot_qt
GR_PLOT_QT(1)                    User Commands                   GR_PLOT_QT(1)

NAME
       gr_plot_qt - plot data using Qt graphics and GNU Radio

DESCRIPTION
       Fancy plot display.

SEE ALSO
       gr_plot_char(1)   gr_plot_const(1)   gr_plot_fft_c(1)  gr_plot_fft_f(1)
       gr_plot_float(1)    gr_plot_int(1)    gr_plot_iq(1)    gr_plot_psd_c(1)
       gr_plot_psd_f(1)  gr_plot_qt(1)  gr_plot_short(1)

gr_plot_qt 3.10.5.1               2023-02-04                     GR_PLOT_QT(1)
```

***

**gr\_read\_file\_metadata**

A Gnu Radio Utility

```
:~# gr_read_file_metadata -h
usage: gr_read_file_metadata [-h] [-D] FILE

Read in a GNU Radio file with meta data, extracts the header and prints it.

positional arguments:
  FILE            Input file

options:
  -h, --help      show this help message and exit
  -D, --detached  Used if header is detached.
```

***

**grcc**

Gnu Radio Companion Compiler

```
:~# grcc -h
usage: grcc [-h] [-o DIR] [-u] [-r] GRC_FILE [GRC_FILE ...]

Compile a GRC file (.grc) into a GNU Radio Python program and run it.

positional arguments:
  GRC_FILE              .grc file to compile

options:
  -h, --help            show this help message and exit
  -o DIR, --output DIR  Output directory for compiled program [default=.]
  -u, --user-lib-dir    Output to default hier_block library (overwrites -o)
  -r, --run             Run the program after compiling [default=False]
```

***

**polar\_channel\_construction**

Gnu Radio Polar Configurator

```
:~# polar_channel_construction -h
POLAR code channel constructor commandline tool
usage: polar_channel_construction [-h] [-c {BEC,AWGN}] [-b BLOCK_SIZE]
                                  [-s DESIGN_SNR] [-k MU]

options:
  -h, --help            show this help message and exit
  -c {BEC,AWGN}, --channel {BEC,AWGN}
                        specify channel, currently BEC or AWGN (default='BEC')
  -b BLOCK_SIZE, --blocksize BLOCK_SIZE
                        specify block size of polar code (default=16)
  -s DESIGN_SNR, --design-snr DESIGN_SNR
                        specify design SNR of polar code (default=0.0)
  -k MU, --mu MU        specify block size of polar code (default=2)
```

***

**tags\_demo**

GNURadio and UHD tags example

```
:~# tags_demo --help
UHD Tags Demo Allowed options:
  --help                             help message
  --addr arg                         the device address in string format
  --rate arg (=1000000)              the sample rate in samples per second
  --freq arg (=10000000)             the center frequency in Hz
  --burst arg (=0.10000000000000001) the duration of each burst in seconds
  --idle arg (=0.050000000000000003) idle time between bursts in seconds
  --length_tag arg                   the length tag key name

The tags sink demo block will print USRP source time stamps.
The tags source demo block will send bursts to the USRP sink.
Look at the USRP output on a scope to see the timed bursts.

```

***

**uhd\_fft**

Display spectrum from UHD receiver

```
:~# uhd_fft -h
Warning: failed to XInitThreads()
usage: uhd_fft [-h] [-a ARGS] [--spec SPEC] [-A ANTENNA] [-s SAMP_RATE]
               [-g GAIN] [-p POWER] -f FREQ [--lo-offset LO_OFFSET]
               [-c CHANNELS] [--lo-export LO_EXPORT] [--lo-source LO_SOURCE]
               [--otw-format {sc16,sc12,sc8}] [--stream-args STREAM_ARGS] [-v]
               [--show-async-msg] [--sync {default,pps,auto}]
               [--clock-source CLOCK_SOURCE] [--time-source TIME_SOURCE]
               [--fft-size FFT_SIZE] [--fft-average {off,low,medium,high}]
               [--avg-alpha AVG_ALPHA] [--update-rate UPDATE_RATE]
               [--phase-relations]

UHD FFT

options:
  -h, --help            show this help message and exit

USRP Arguments:
  -a ARGS, --args ARGS  UHD device address args
  --spec SPEC           Subdevice(s) of UHD device where appropriate. Use a
                        comma-separated list to set different boards to
                        different specs.
  -A ANTENNA, --antenna ANTENNA
                        Select Rx antenna(s) where appropriate
  -s SAMP_RATE, --samp-rate SAMP_RATE
                        Sample rate
  -g GAIN, --gain GAIN  Gain (default is midpoint)
  -p POWER, --power POWER
                        (Reference) power level (in dBm). Not supported by all
                        devices (see UHD manual). Will fail if not supported.
                        Precludes --gain. Behaviour may differ between
                        applications.
  -f FREQ, --freq FREQ  Set carrier frequency to FREQ
  --lo-offset LO_OFFSET
                        Set daughterboard LO offset to OFFSET [default=hw
                        default]
  -c CHANNELS, --channels CHANNELS
                        Select Rx Channels
  --lo-export LO_EXPORT
                        Set TwinRX LO export {None, True, False} for each
                        channel with a comma-separated list. None skips a
                        channel.
  --lo-source LO_SOURCE
                        Set TwinRX LO source {None, internal, companion,
                        external} for each channel with a comma-separated
                        list. None skips this channel.
  --otw-format {sc16,sc12,sc8}
                        Choose over-the-wire data format
  --stream-args STREAM_ARGS
                        Set additional stream arguments
  -v, --verbose         Use verbose console output
  --show-async-msg      Show asynchronous message notifications from UHD
  --sync {default,pps,auto}
                        Set to 'pps' to sync devices to PPS
  --clock-source CLOCK_SOURCE
                        Set the clock source; typically 'internal', 'external'
                        or 'gpsdo'
  --time-source TIME_SOURCE
                        Set the time source

UHD FFT Arguments:
  --fft-size FFT_SIZE   Set number of FFT bins
  --fft-average {off,low,medium,high}
                        Set FFT averaging
  --avg-alpha AVG_ALPHA
                        Specify FFT average alpha (overrides --fft-average)
  --update-rate UPDATE_RATE
                        Set GUI widget update period in seconds
  --phase-relations     Plot relative phases between multiple channels
```

***

**uhd\_rx\_cfile**

Save UHD received data

```
:~# uhd_rx_cfile -h
Usage: uhd_rx_cfile: [options] output_filename

Options:
  -h, --help            show this help message and exit
  -a ARGS, --args=ARGS  UHD device address args , [default=]
  --spec=SPEC           Subdevice of UHD device where appropriate
  -c CHANNELS, --channels=CHANNELS
                        Select receive channels
  -A ANTENNA, --antenna=ANTENNA
                        Select Rx Antenna(s) where appropriate. Use a comma-
                        delimited list if different channels have different
                        antenna ports.
  -r SAMP_RATE, --samp-rate=SAMP_RATE
                        Set sample rate (bandwidth) [default=1000000.0]
  -f FREQ, --freq=FREQ  Set frequency to FREQ
  --lo-offset=LO_OFFSET
                        Set daughterboard LO offset to OFFSET [default=hw
                        default]
  -g GAIN, --gain=GAIN  Set gain in dB (default is midpoint)
  --normalized-gain     Specify gain as normalized value (in [0, 1])
  -m, --metafile        output metadata to file [default=False]
  -s, --output-shorts   Output interleaved shorts instead of complex floats
  -N NSAMPLES, --nsamples=NSAMPLES
                        Number of samples to collect [default=+inf]
  -v, --verbose         verbose output
  --wire-format=WIRE_FORMAT
                        Set wire format from USRP [default=sc16
  --stream-args=STREAM_ARGS
                        Set additional stream arguments
  --show-async-msg      Show asynchronous message notifications from UHD
                        [default=False]
  --sync=SYNC           Set to 'pps' to sync devices to PPS instead of
                        internal.
```

***

**uhd\_rx\_nogui**

GNU Radio receiver

```
:~# uhd_rx_nogui -h
usage: uhd_rx_nogui [-h] [-a ARGS] [--spec SPEC] [-A ANTENNA] [-f Hz] [-c Hz]
                    [-g dB] [-m TYPE] [-o RATE] [-r dB] [-p FREQ]
                    [-O AUDIO_OUTPUT] [--show-async-msg]

options:
  -h, --help            show this help message and exit
  -a ARGS, --args ARGS  UHD device address args
  --spec SPEC           Subdevice of UHD device where appropriate
  -A ANTENNA, --antenna ANTENNA
                        select Rx Antenna where appropriate
  -f Hz, --frequency Hz
                        set receive frequency to Hz
  -c Hz, --calibration Hz
                        set frequency offset to Hz
  -g dB, --gain dB      set RF gain [default is midpoint]
  -m TYPE, --modulation TYPE
                        set modulation type (AM,FM,WFM)
  -o RATE, --output-rate RATE
                        set audio output rate to RATE
  -r dB, --rf-squelch dB
                        set RF squelch to dB [default=-50.0]
  -p FREQ, --ctcss FREQ
                        set CTCSS squelch to FREQ
  -O AUDIO_OUTPUT, --audio-output AUDIO_OUTPUT
                        pcm device name. E.g., hw:0,0 or surround51 or
                        /dev/dsp
  --show-async-msg      Show asynchronous message notifications from UHD
```

***

**uhd\_siggen**

Signal Generator using UHD hardware

```
:~# uhd_siggen -h
usage: uhd_siggen [-h] [-a ARGS] [--spec SPEC] [-A ANTENNA] [-s SAMP_RATE]
                  [-g GAIN] [-p POWER] -f FREQ [--lo-offset LO_OFFSET]
                  [-c CHANNELS] [--lo-export LO_EXPORT]
                  [--lo-source LO_SOURCE] [--otw-format {sc16,sc12,sc8}]
                  [--stream-args STREAM_ARGS] [-v] [--show-async-msg]
                  [--sync {default,pps,auto}] [--clock-source CLOCK_SOURCE]
                  [--time-source TIME_SOURCE] [-m AMPL] [-x WAVEFORM_FREQ]
                  [-y WAVEFORM2_FREQ] [--sine] [--const] [--offset OFFSET]
                  [--gaussian] [--uniform] [--2tone] [--sweep]

USRP Signal Generator.

options:
  -h, --help            show this help message and exit

USRP Arguments:
  -a ARGS, --args ARGS  UHD device address args
  --spec SPEC           Subdevice(s) of UHD device where appropriate. Use a
                        comma-separated list to set different boards to
                        different specs.
  -A ANTENNA, --antenna ANTENNA
                        Select Tx antenna(s) where appropriate
  -s SAMP_RATE, --samp-rate SAMP_RATE
                        Sample rate
  -g GAIN, --gain GAIN  Gain (default is midpoint)
  -p POWER, --power POWER
                        (Reference) power level (in dBm). Not supported by all
                        devices (see UHD manual). Will fail if not supported.
                        Precludes --gain. Behaviour may differ between
                        applications.
  -f FREQ, --freq FREQ  Set carrier frequency to FREQ
  --lo-offset LO_OFFSET
                        Set daughterboard LO offset to OFFSET [default=hw
                        default]
  -c CHANNELS, --channels CHANNELS
                        Select Tx Channels
  --lo-export LO_EXPORT
                        Set TwinRX LO export {None, True, False} for each
                        channel with a comma-separated list. None skips a
                        channel.
  --lo-source LO_SOURCE
                        Set TwinRX LO source {None, internal, companion,
                        external} for each channel with a comma-separated
                        list. None skips this channel.
  --otw-format {sc16,sc12,sc8}
                        Choose over-the-wire data format
  --stream-args STREAM_ARGS
                        Set additional stream arguments
  -v, --verbose         Use verbose console output
  --show-async-msg      Show asynchronous message notifications from UHD
  --sync {default,pps,auto}
                        Set to 'pps' to sync devices to PPS
  --clock-source CLOCK_SOURCE
                        Set the clock source; typically 'internal', 'external'
                        or 'gpsdo'
  --time-source TIME_SOURCE
                        Set the time source

Siggen Arguments:
  -m AMPL, --amplitude AMPL
                        Set output amplitude to AMPL (0.0-1.0). Note that if
                        --power is given, UHD will attempt to match the output
                        power regardless of the amplitude.
  -x WAVEFORM_FREQ, --waveform-freq WAVEFORM_FREQ
                        Set baseband waveform frequency to FREQ
  -y WAVEFORM2_FREQ, --waveform2-freq WAVEFORM2_FREQ
                        Set 2nd waveform frequency to FREQ
  --sine                Generate a carrier modulated by a complex sine wave
  --const               Generate a constant carrier
  --offset OFFSET       Set waveform phase offset to OFFSET
  --gaussian            Generate Gaussian random output
  --uniform             Generate Uniform random output
  --2tone               Generate Two Tone signal for IMD testing
  --sweep               Generate a swept sine wave
```

***

**uhd\_siggen\_gui**

GNU Radio signal generator using UHD hardware

```
:~# uhd_siggen_gui -h
Warning: failed to XInitThreads()
usage: uhd_siggen_gui [-h] [-a ARGS] [--spec SPEC] [-A ANTENNA] [-s SAMP_RATE]
                      [-g GAIN] [-p POWER] -f FREQ [--lo-offset LO_OFFSET]
                      [-c CHANNELS] [--lo-export LO_EXPORT]
                      [--lo-source LO_SOURCE] [--otw-format {sc16,sc12,sc8}]
                      [--stream-args STREAM_ARGS] [-v] [--show-async-msg]
                      [--sync {default,pps,auto}]
                      [--clock-source CLOCK_SOURCE]
                      [--time-source TIME_SOURCE] [-m AMPL] [-x WAVEFORM_FREQ]
                      [-y WAVEFORM2_FREQ] [--sine] [--const] [--offset OFFSET]
                      [--gaussian] [--uniform] [--2tone] [--sweep] [-q]

USRP Signal Generator.

options:
  -h, --help            show this help message and exit

USRP Arguments:
  -a ARGS, --args ARGS  UHD device address args
  --spec SPEC           Subdevice(s) of UHD device where appropriate. Use a
                        comma-separated list to set different boards to
                        different specs.
  -A ANTENNA, --antenna ANTENNA
                        Select Tx antenna(s) where appropriate
  -s SAMP_RATE, --samp-rate SAMP_RATE
                        Sample rate
  -g GAIN, --gain GAIN  Gain (default is midpoint)
  -p POWER, --power POWER
                        (Reference) power level (in dBm). Not supported by all
                        devices (see UHD manual). Will fail if not supported.
                        Precludes --gain. Behaviour may differ between
                        applications.
  -f FREQ, --freq FREQ  Set carrier frequency to FREQ
  --lo-offset LO_OFFSET
                        Set daughterboard LO offset to OFFSET [default=hw
                        default]
  -c CHANNELS, --channels CHANNELS
                        Select Tx Channels
  --lo-export LO_EXPORT
                        Set TwinRX LO export {None, True, False} for each
                        channel with a comma-separated list. None skips a
                        channel.
  --lo-source LO_SOURCE
                        Set TwinRX LO source {None, internal, companion,
                        external} for each channel with a comma-separated
                        list. None skips this channel.
  --otw-format {sc16,sc12,sc8}
                        Choose over-the-wire data format
  --stream-args STREAM_ARGS
                        Set additional stream arguments
  -v, --verbose         Use verbose console output
  --show-async-msg      Show asynchronous message notifications from UHD
  --sync {default,pps,auto}
                        Set to 'pps' to sync devices to PPS
  --clock-source CLOCK_SOURCE
                        Set the clock source; typically 'internal', 'external'
                        or 'gpsdo'
  --time-source TIME_SOURCE
                        Set the time source

Siggen Arguments:
  -m AMPL, --amplitude AMPL
                        Set output amplitude to AMPL (0.0-1.0). Note that if
                        --power is given, UHD will attempt to match the output
                        power regardless of the amplitude.
  -x WAVEFORM_FREQ, --waveform-freq WAVEFORM_FREQ
                        Set baseband waveform frequency to FREQ
  -y WAVEFORM2_FREQ, --waveform2-freq WAVEFORM2_FREQ
                        Set 2nd waveform frequency to FREQ
  --sine                Generate a carrier modulated by a complex sine wave
  --const               Generate a constant carrier
  --offset OFFSET       Set waveform phase offset to OFFSET
  --gaussian            Generate Gaussian random output
  --uniform             Generate Uniform random output
  --2tone               Generate Two Tone signal for IMD testing
  --sweep               Generate a swept sine wave

GUI Arguments:
  -q, --show-freq-sink  Show QT Frequency Widget
```

***

#### gnuradio-dev <a href="#gnuradio-dev" id="gnuradio-dev"></a>

Header files for the GNU Radio software defined radio system. Since GNU Radio is a framework for development of SDR applications, you are likely to need this installed.

Part of the main gnuradio build.

**Installed size:** `2.55 MB`\
**How to install:** `sudo apt install gnuradio-dev`

<details>

<summary>Dependencies:</summary>

* gnuradio
* libboost-date-time1.74-dev
* libboost-filesystem1.74-dev
* libboost-program-options1.74-dev
* libboost-regex1.74-dev
* libboost-system1.74-dev
* libboost-test1.74-dev
* libboost-thread1.74-dev
* libcppunit-dev
* libfftw3-dev
* libgmp-dev
* libgsm1-dev
* libspdlog-dev
* libthrift-dev
* libvolk2-dev
* pybind11-dev
* python3-dev

</details>

***

#### gnuradio-doc <a href="#gnuradio-doc" id="gnuradio-doc"></a>

Documentation for the GNU Radio software defined radio system in html and xml form.

Part of the main gnuradio build.

**Installed size:** `249.87 MB`\
**How to install:** `sudo apt install gnuradio-doc`

***

#### libgnuradio-analog3.10.5 <a href="#libgnuradio-analog3105" id="libgnuradio-analog3105"></a>

Library for handling analog signal processing functions. These functions are also in gnuradio-core. Part of the main gnuradio build.

**Installed size:** `662 KB`\
**How to install:** `sudo apt install libgnuradio-analog3.10.5`

<details>

<summary>Dependencies:</summary>

* libc6
* libfmt9
* libgcc-s1
* libgnuradio-blocks3.10.5
* libgnuradio-fft3.10.5
* libgnuradio-pmt3.10.5
* libgnuradio-runtime3.10.5
* libspdlog1.10-fmt9
* libstdc++6
* libvolk2.5

</details>

***

#### libgnuradio-audio3.10.5 <a href="#libgnuradio-audio3105" id="libgnuradio-audio3105"></a>

This is the gr-audio library, used to connect to audio sources (mic-in) and sinks (speaker-out) ports on a computer. The underlying hardware driver is system and OS dependent and this module should automatically discover the correct one to use. Part of the main gnuradio build.

**Installed size:** `554 KB`\
**How to install:** `sudo apt install libgnuradio-audio3.10.5`

<details>

<summary>Dependencies:</summary>

* libasound2
* libboost-thread1.74.0
* libc6
* libfmt9
* libgcc-s1
* libgnuradio-pmt3.10.5
* libgnuradio-runtime3.10.5
* libjack-jackd2-0 | libjack-0.125
* libportaudio2
* libspdlog1.10-fmt9
* libstdc++6

</details>

***

#### libgnuradio-blocks3.10.5 <a href="#libgnuradio-blocks3105" id="libgnuradio-blocks3105"></a>

Some non-signal processing blocks. These functions are also in gnuradio-core. Part of the main gnuradio build.

**Installed size:** `3.02 MB`\
**How to install:** `sudo apt install libgnuradio-blocks3.10.5`

<details>

<summary>Dependencies:</summary>

* libboost-thread1.74.0
* libc6
* libfmt9
* libgcc-s1
* libgnuradio-pmt3.10.5
* libgnuradio-runtime3.10.5
* libsndfile1
* libspdlog1.10-fmt9
* libstdc++6
* libvolk2.5

</details>

***

#### libgnuradio-channels3.10.5 <a href="#libgnuradio-channels3105" id="libgnuradio-channels3105"></a>

Some channel oriented processing blocks. These functions are also in gnuradio-core. Part of the main gnuradio build.

**Installed size:** `466 KB`\
**How to install:** `sudo apt install libgnuradio-channels3.10.5`

<details>

<summary>Dependencies:</summary>

* libc6
* libgcc-s1
* libgnuradio-analog3.10.5
* libgnuradio-blocks3.10.5
* libgnuradio-filter3.10.5
* libgnuradio-pmt3.10.5
* libgnuradio-runtime3.10.5
* libstdc++6
* libvolk2.5

</details>

***

#### libgnuradio-digital3.10.5 <a href="#libgnuradio-digital3105" id="libgnuradio-digital3105"></a>

All the functions for doing digital modulation and demodulation, including bpsk, qpsk, gmsk and ofdm signals. Part of the main gnuradio build.

**Installed size:** `1.67 MB`\
**How to install:** `sudo apt install libgnuradio-digital3.10.5`

<details>

<summary>Dependencies:</summary>

* libc6
* libfmt9
* libgcc-s1
* libgnuradio-analog3.10.5
* libgnuradio-blocks3.10.5
* libgnuradio-filter3.10.5
* libgnuradio-pmt3.10.5
* libgnuradio-runtime3.10.5
* libspdlog1.10-fmt9
* libstdc++6
* libvolk2.5

</details>

***

#### libgnuradio-dtv3.10.5 <a href="#libgnuradio-dtv3105" id="libgnuradio-dtv3105"></a>

ATSC support, gr-atsc ported to a new framework, as well as DVB-S2, DVB-T, DVB-T2 digital video broadcast standards. Part of the main gnuradio build.

**Installed size:** `1.40 MB`\
**How to install:** `sudo apt install libgnuradio-dtv3.10.5`

<details>

<summary>Dependencies:</summary>

* libc6
* libfmt9
* libgcc-s1
* libgnuradio-fec3.10.5
* libgnuradio-fft3.10.5
* libgnuradio-filter3.10.5
* libgnuradio-pmt3.10.5
* libgnuradio-runtime3.10.5
* libspdlog1.10-fmt9
* libstdc++6
* libvolk2.5

</details>

***

#### libgnuradio-fec3.10.5 <a href="#libgnuradio-fec3105" id="libgnuradio-fec3105"></a>

Handle forward error correction processing in gnuradio. Implements the GNU Radio FEC API, supporting encoders and decoders for no-op dummmy, repetition, and convolutional classes. Part of the main gnuradio build.

**Installed size:** `947 KB`\
**How to install:** `sudo apt install libgnuradio-fec3.10.5`

<details>

<summary>Dependencies:</summary>

* libc6
* libfmt9
* libgcc-s1
* libgnuradio-blocks3.10.5
* libgnuradio-pmt3.10.5
* libgnuradio-runtime3.10.5
* libgsl27
* libspdlog1.10-fmt9
* libstdc++6
* libvolk2.5

</details>

***

#### libgnuradio-fft3.10.5 <a href="#libgnuradio-fft3105" id="libgnuradio-fft3105"></a>

Library for Fourier transform techniques used in gnuradio. Uses single precision FFT from libfftw3-single3. Part of the main gnuradio build.

**Installed size:** `326 KB`\
**How to install:** `sudo apt install libgnuradio-fft3.10.5`

<details>

<summary>Dependencies:</summary>

* libc6
* libfftw3-single3
* libfmt9
* libgcc-s1
* libgnuradio-pmt3.10.5
* libgnuradio-runtime3.10.5
* libspdlog1.10-fmt9
* libstdc++6
* libvolk2.5

</details>

***

#### libgnuradio-filter3.10.5 <a href="#libgnuradio-filter3105" id="libgnuradio-filter3105"></a>

Library of filter blocks used in gnuradio. Implements FIR, IIR and FFT filters, as well as Polyphase filterbank and PFB arbitrary resampler methods. Part of the main gnuradio build.

**Installed size:** `1.02 MB`\
**How to install:** `sudo apt install libgnuradio-filter3.10.5`

<details>

<summary>Dependencies:</summary>

* libc6
* libfmt9
* libgcc-s1
* libgnuradio-fft3.10.5
* libgnuradio-pmt3.10.5
* libgnuradio-runtime3.10.5
* libspdlog1.10-fmt9
* libstdc++6
* libvolk2.5

</details>

***

#### libgnuradio-iio3.10.5 <a href="#libgnuradio-iio3105" id="libgnuradio-iio3105"></a>

Libiio is a library that has been conceived to ease the development of applications interfacing Industrial Input/Output (IIO) devices through the IIO subsystem of the Linux kernel.

The IIO blocks for GnuRadio can be used to create flowgraphs that interface IIO devices through libiio.

Part of the main gnuradio build.

**Installed size:** `550 KB`\
**How to install:** `sudo apt install libgnuradio-iio3.10.5`

<details>

<summary>Dependencies:</summary>

* libad9361-0
* libboost-thread1.74.0
* libc6
* libfmt9
* libgcc-s1
* libgnuradio-pmt3.10.5
* libgnuradio-runtime3.10.5
* libiio0
* libspdlog1.10-fmt9
* libstdc++6
* libvolk2.5

</details>

***

#### libgnuradio-network3.10.5 <a href="#libgnuradio-network3105" id="libgnuradio-network3105"></a>

Library of blocks that implement UDP and TCP source and sink blocks supporting both IPv4 and IPv6. Part of the main gnuradio build.

**Installed size:** `606 KB`\
**How to install:** `sudo apt install libgnuradio-network3.10.5`

<details>

<summary>Dependencies:</summary>

* libboost-thread1.74.0
* libc6
* libfmt9
* libgcc-s1
* libgnuradio-pmt3.10.5
* libgnuradio-runtime3.10.5
* libspdlog1.10-fmt9
* libstdc++6

</details>

***

#### libgnuradio-pdu3.10.5 <a href="#libgnuradio-pdu3105" id="libgnuradio-pdu3105"></a>

Protocol Data Units library provides signal processing blocks that operate on Protocol Data Unit format messages. Many such blocks are analogs of streaming API functionality. Part of the main gnuradio build.

**Installed size:** `638 KB`\
**How to install:** `sudo apt install libgnuradio-pdu3.10.5`

<details>

<summary>Dependencies:</summary>

* libc6
* libfmt9
* libgcc-s1
* libgnuradio-pmt3.10.5
* libgnuradio-runtime3.10.5
* libspdlog1.10-fmt9
* libstdc++6

</details>

***

#### libgnuradio-pmt3.10.5 <a href="#libgnuradio-pmt3105" id="libgnuradio-pmt3105"></a>

Polymorphic Types are opaque data types that are designed as generic containers of data that can be safely passed around between blocks and threads in GNU Radio. Part of the main gnuradio build.

**Installed size:** `394 KB`\
**How to install:** `sudo apt install libgnuradio-pmt3.10.5`

<details>

<summary>Dependencies:</summary>

* libc6
* libgcc-s1
* libstdc++6
* libvolk2.5

</details>

***

#### libgnuradio-qtgui3.10.5 <a href="#libgnuradio-qtgui3105" id="libgnuradio-qtgui3105"></a>

QT-based graphical sinks for gnuradio applications. Implements opengl, raster and native plotting methods, and supports a QT Style Sheet (QSS) file to adjust the look. Part of the main gnuradio build.

**Installed size:** `1.83 MB`\
**How to install:** `sudo apt install libgnuradio-qtgui3.10.5`

<details>

<summary>Dependencies:</summary>

* libc6
* libfmt9
* libgcc-s1
* libgnuradio-fft3.10.5
* libgnuradio-filter3.10.5
* libgnuradio-pmt3.10.5
* libgnuradio-runtime3.10.5
* libqt5core5a
* libqt5gui5 | libqt5gui5-gles
* libqt5widgets5
* libqwt-qt5-6
* libspdlog1.10-fmt9
* libstdc++6
* libvolk2.5

</details>

***

#### libgnuradio-runtime3.10.5 <a href="#libgnuradio-runtime3105" id="libgnuradio-runtime3105"></a>

Top level component library. Defines core blocks. Handles settings for logging, performance counters, and control port. Part of the main gnuradio build.

**Installed size:** `1.97 MB`\
**How to install:** `sudo apt install libgnuradio-runtime3.10.5`

<details>

<summary>Dependencies:</summary>

* libboost-program-options1.74.0
* libboost-thread1.74.0
* libc6
* libfmt9
* libgcc-s1
* libgmp10
* libgnuradio-pmt3.10.5
* libspdlog1.10-fmt9
* libstdc++6
* libthrift-0.17.0
* libunwind8
* libvolk2.5

</details>

***

#### libgnuradio-soapy3.10.5 <a href="#libgnuradio-soapy3105" id="libgnuradio-soapy3105"></a>

Soapy hardware drivers using the SoapySDR driver framework. Part of the main gnuradio build.

**Installed size:** `462 KB`\
**How to install:** `sudo apt install libgnuradio-soapy3.10.5`

<details>

<summary>Dependencies:</summary>

* libc6
* libfmt9
* libgcc-s1
* libgmp10
* libgnuradio-pmt3.10.5
* libgnuradio-runtime3.10.5
* libsoapysdr0.8
* libspdlog1.10-fmt9
* libstdc++6

</details>

***

#### libgnuradio-trellis3.10.5 <a href="#libgnuradio-trellis3105" id="libgnuradio-trellis3105"></a>

Library for trellis coding modulation, including the Viterbi Algorithm, Concatenated Coding and Turbo Decoding based upon finite state machine (FSM) class. Part of the main gnuradio build.

**Installed size:** `1.00 MB`\
**How to install:** `sudo apt install libgnuradio-trellis3.10.5`

<details>

<summary>Dependencies:</summary>

* libc6
* libfmt9
* libgcc-s1
* libgnuradio-pmt3.10.5
* libgnuradio-runtime3.10.5
* libspdlog1.10-fmt9
* libstdc++6

</details>

***

#### libgnuradio-uhd3.10.5 <a href="#libgnuradio-uhd3105" id="libgnuradio-uhd3105"></a>

The gnuradio interface to the UHD library to connect to and send and receive data between to the Ettus Research, LLC product line - including the USRP family of software radio peripheral devices. Part of the main gnuradio build.

**Installed size:** `674 KB`\
**How to install:** `sudo apt install libgnuradio-uhd3.10.5`

<details>

<summary>Dependencies:</summary>

* libboost-thread1.74.0
* libc6
* libfmt9
* libgcc-s1
* libgnuradio-pmt3.10.5
* libgnuradio-runtime3.10.5
* libspdlog1.10-fmt9
* libstdc++6
* libuhd4.3.0
* libvolk2.5

</details>

***

#### libgnuradio-video-sdl3.10.5 <a href="#libgnuradio-video-sdl3105" id="libgnuradio-video-sdl3105"></a>

Library for handling SDL (Simple DirectMedia Layer) video data. Implements input and output blocks. Part of the main gnuradio build.

**Installed size:** `238 KB`\
**How to install:** `sudo apt install libgnuradio-video-sdl3.10.5`

<details>

<summary>Dependencies:</summary>

* libc6
* libfmt9
* libgcc-s1
* libgnuradio-pmt3.10.5
* libgnuradio-runtime3.10.5
* libsdl1.2debian
* libspdlog1.10-fmt9
* libstdc++6

</details>

***

#### libgnuradio-vocoder3.10.5 <a href="#libgnuradio-vocoder3105" id="libgnuradio-vocoder3105"></a>

Library of vocoder blocks, including ulaw, alaw, gsm and codec2. Debian uses external libraries for gsm and codec2.

Part of the main gnuradio build.

**Installed size:** `318 KB`\
**How to install:** `sudo apt install libgnuradio-vocoder3.10.5`

<details>

<summary>Dependencies:</summary>

* libc6
* libcodec2-1.0
* libfmt9
* libgcc-s1
* libgnuradio-pmt3.10.5
* libgnuradio-runtime3.10.5
* libgsm1
* libspdlog1.10-fmt9
* libstdc++6

</details>

***

#### libgnuradio-wavelet3.10.5 <a href="#libgnuradio-wavelet3105" id="libgnuradio-wavelet3105"></a>

Library of Daubechies wavelet function blocks. wvps computes the Wavelet Power Spectrum from a set of wavelet coefficients.

Part of the main gnuradio build.

**Installed size:** `110 KB`\
**How to install:** `sudo apt install libgnuradio-wavelet3.10.5`

<details>

<summary>Dependencies:</summary>

* libc6
* libgcc-s1
* libgnuradio-pmt3.10.5
* libgnuradio-runtime3.10.5
* libgsl27
* libstdc++6

</details>

***

#### libgnuradio-zeromq3.10.5 <a href="#libgnuradio-zeromq3105" id="libgnuradio-zeromq3105"></a>

0MQ messaging library support. Provide network socket endpoints for gnuradio data and message streams. PUB/SUB, PUSH/PULL, REP/REQ models supported.

Part of the main gnuradio build.

**Installed size:** `382 KB`\
**How to install:** `sudo apt install libgnuradio-zeromq3.10.5`

<details>

<summary>Dependencies:</summary>

* libc6
* libfmt9
* libgcc-s1
* libgnuradio-pmt3.10.5
* libgnuradio-runtime3.10.5
* libspdlog1.10-fmt9
* libstdc++6
* libzmq5

</details>

***

Updated on: 2023-Mar-08\


***
