# wustl-ris-registry-extended <img src="img/ris_logo.png" align="right" width="125px" />

[![Under Development](https://img.shields.io/badge/status-under%20development-red.svg)](https://github.com/the-mad-statter/wustl-ris-registry-extended)
[![Last Commit](https://img.shields.io/github/last-commit/the-mad-statter/wustl-ris-registry-extended.svg)](https://github.com/the-mad-statter/wustl-ris-registry-extended/commits/master)

## Overview

This repository contains Dockerfiles for different Docker containers for use on the [Washington University Scientific Compute Platform](https://docs.ris.wustl.edu/doc/compute/02_compute.html)

## Prerequisites

1. [Activate Compute Services](https://ris.wustl.edu/services/compute/resources/)
2. Install [Git](https://git-scm.com/downloads)
3. Create [Docker Hub Account](https://hub.docker.com/)
4. Install [Docker](https://docs.docker.com/get-docker/)

## Prepare Container

1. `git clone https://github.com/the-mad-statter/wustl-ris-registry-extended`
2. navigate to desired Dockerfile directory
3. `docker build -t <your_dockerhub_username>/<image_name>:<tag> .`
4. `docker push <your_dockerhub_username>/<image_name>:<tag>`

## Run the Container on the Compute Platform

1. ssh into the compute platform
2. submit a job

## About

### Washington University in Saint Louis <img src="img/brookings_seal.png" align="right" width="125px"/>

Established in 1853, [Washington University in Saint
Louis](https://www.wustl.edu) is among the world’s leaders in teaching,
research, patient care, and service to society. Bosting 24 Nobel
laureates to date, the University is ranked 7th in the world for most
cited researchers, received the 4th highest amount of NIH medical
research grants among medical schools in 2019, and was tied for 1st in
the United States for genetics and genomics in 2018. The University is
committed to learning and exploration, discovery and impact, and
intellectual passions and challenging the unknown.