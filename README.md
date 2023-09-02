Tested on Ubuntu 22.04 in WSL

Pre-requisites:
`apt-install g++ libboost-all-dev libssl dev`

This *MUST* be compiled with the `-lssl` and `-lcrypto` flags.
`g++ main.cpp -o neo -lssl -lcrypto`

Usage:
Get Near Earth Objects (NEOs) from NASA API. You must obtain a [NASA API key](https://api.nasa.gov/). It's free and easy, and grants you access to [more than NEOs](https://api.nasa.gov/).
`neo <your api key> <start_date> <end_date>`

Note: the dates are in `YYYY-MM-DD` format.

Why is this code to make a simple API call so complicated one might ask?

Looking back at it, this is writing an HTTP client from scratch as opposed to using an already pre-existing HTTP client, such as [CPR](https://github.com/libcpr/cpr).

This example is quite literally built on the Beast library from Boost. All I did was change a few things and borrow the `root_certificates.hpp` from their examples in GitHub.