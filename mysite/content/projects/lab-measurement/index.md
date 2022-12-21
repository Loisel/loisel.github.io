---
title: "lab::measurement"
date: 2022-12-20T15:11:59+01:00
startdate: 2013-01-20
draft: false
description: "Control and measurement software for measurement devices. Supports multiple device interfaces."
image: "logo.png"
giturl: "https://github.com/lab-measurement/lab-measurement"
languages: "Perl"
technologies: "GPIB, NI-VISA"
---

Lab::measurement has been developed by [Andrea Hüttel](https://www.akhuettel.de/) and others to
facilitate the measurement process in a physics lab. It allows for easy setup and simultaneous
control of multiple devices
connected to different interfaces (e.g., GPIB, NI-VISA, COM). Results can be plotted on-the-go
using gnuplot. Here is a small example script measuring an I-V curve:
```perl
use Lab::Moose; # you get 'use warnings; use strict;' for free
 
my $source = instrument(
    type            => 'YokogawaGS200',
    connection_type => 'USB',
    # Safety limits:
    max_units => 10, min_units => -10,
    max_units_per_step => 0.1, max_units_per_second => 1
);
 
my $dmm = instrument(type => 'Agilent34410A', connection_type => 'USB');
 
my $sweep = sweep(
    type       => 'Step::Voltage',
    instrument => $source,
    from => -5, to => 5, step => 0.01
);
 
my $datafile = sweep_datafile(columns => [qw/voltage current/]);
 
my $meas = sub {
    my $sweep = shift;
    $sweep->log(
        voltage => $source->cached_level(),
        current => $dmm->get_value(),
    );
};
 
$sweep->start(
    measurement => $meas,
    datafile    => $datafile,
);
```

I joined the team during my PhD thesis in Regensburg around 2012. My main contributions were device
specific drivers and a generalization of the sweep functionality, if I remember correctly -- 
I have a hard 
time recovering my contributions in the Github repository, maybe there was some hickup.
A more detailed description of the software can be found in [Huettel et al.](https://www.sciencedirect.com/science/article/pii/S0010465518302819?via%3Dihub).
