---
layout: page
title: Projects
---

These are projects I've worked on, with a summary of the work accomplished.

### pyFxTrader &mdash; A Forex backtesting platform and live trader (2017)

I contributed as a freelancing software developer to [pyFxTrader](https://github.com/jmelett/pyfx), an open-source Forex backtesting platform written in Python. The platform gives you an interface to query a stream of past financial data (i.e. candles) in order to compute indicators and test your automated trading strategies. It is meant to give you maximum modularity in designing your strategy which you can implement in Python or your own language. The platform allows you to backtest your strategy using various timeframes (i.e. M5, M15, H1, H2) and across several currencies (e.g. EURUSD).

My contributions revolved mostly around applying optimizations and guaranteeing the validity of the data being fed through the stream. This way it is possible to quickly obtain results on the performance of a strategy and make tweaks accordingly. As a general reference, a non-trivial strategy based on a few indicators can be backtested on a month worth of data in one currency in about 10 minutes on a home computer.

Through this project I got close and personal with automated trading as well, and helped implement a winning strategy.


### WIRE &mdash; Web Interfaced Reverb Engine (2016)

This project consists of a convolution reverb which can be easily accessed and used through a [Web based frontend](https://stzr1123.github.io/assets/wire_app_screenshot.png). This software is capable of taking a ["dry" sound](https://stzr1123.github.io/assets/avril.wav) and emulating the reverb qualities of a real space (e.g. [the Booth business school atrium](https://stzr1123.github.io/assets/Booth_atrium.wav)). The end result is a [sound file](https://stzr1123.github.io/assets/avril_convolved_with Booth_atrium.wav) which appears to be recorded from within that particular real space.

At the same time, the software can generate visualizations of the [waveforms](https://stzr1123.github.io/assets/Booth_atrium_waveform.png) and [spectrograms](https://stzr1123.github.io/assets/Booth_atrium_spectrogram.png) in order to aid in understanding your transformed audio files.

The project also incorporates some other sound transformations one of which is ring modulation which can make a recording of your voice [sound like R2D2](https://stzr1123.github.io/assets/R2D2_voice_ring_modulation_at_2000_Hz.wav), among other things.

Lastly, it incorporates a reverb recognition analysis module which is capable of extracting the reverb signature present in a "wet" sound and matching it to the reverb response from one of the studied real spaces. That way, if you input a sound file which was recorded inside the atrium of the Booth school of business, the software will be able to detect this with a certain degree of accuracy. You can read more about this module in its [documentation](https://github.com/jkyl/conv_reverb/tree/master/conv_reverb/reverb_analysis).

This project lives on [Github](https://github.com/jkyl/conv_reverb).
