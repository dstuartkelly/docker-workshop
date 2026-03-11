# What's in this Repo?
This repository contains my CA1 assignment submission for module **B8IS003 CLOUD INFRASTRUCTURE AND VIRTUALISATION (B8IS003_2526_TMD2)** 

## Assignment Task:
> Follow the Docker Guide up to and including the deployment of multiple containers using compose.  
> Please submit all sources via Git link, along with any relevant deployment links.

## Assumptions and Constraints
Docker [Getting Started Workshop](https://docs.docker.com/get-started/workshop/) can be found in the documentation section of the Docker website.

For the purposes of this assignment, all work was carried out locally on an Ubuntu 24.04 system. The main relevant files have been copied to this repository as part of the submission and are described in the [File Listing](#file-listing) section below.

The workshop states that the following tasks will be performed.
- Build and run an image as a container.
- Share images using Docker Hub.
- Deploy Docker applications using multiple containers with a database.
- Run applications using Docker Compose.

The work for the assignment will include Parts 1 to 7 only as parts 8 and 9 discuss Best Practices and Further reading after completing the workshop.

## How to use this Repo
Documents in this submission have been created using GitHub Markdown.

I have created separate files Part1.md through Part7.md. Each of these files corresponds to the specific part of the Docker workshop.  
When reviewing the contents, you should start with Part1.md and work through to Part7.md. I have included navigation links in each document so that it can be browsed natively on the GitHub website without having to go back to the file listing each time.

Supporting files for Part 1 and Part 6 have been included in the files directory of the repository.

Links to other repositories used for the Getting-Started Application itself, and the generated Docker images have been included in the [Relevant Links](#relevant-links) section of this document.

## Relevant links
- This Repository https://GitHub.com/dstuartkelly/docker-workshop  
- Getting Started App https://GitHub.com/dstuartkelly/docker-getting-started-app  
- Docker Hub for Getting Started App https://hub.docker.com/r/dstuartkelly/getting-started  

## File Listing
- [Root](./)  
    - [Part1.md](./Part1.md) Part 1 of docker workshop  
    - [Part2.md](./Part2.md) Part 2 of docker workshop  
    - [Part3.md](./Part3.md) Part 3 of docker workshop  
    - [Part4.md](./Part4.md) Part 4 of docker workshop  
    - [Part5.md](./Part5.md) Part 5 of docker workshop  
    - [Part6.md](./Part6.md) Part 6 of docker workshop  
    - [Part7.md](./Part7.md) Part 7 of docker workshop  
    - [README.md](./README.md) This file

- [files](./files/) directory used to store files relevant to this assignment  
    - [Dockerfile](./files/Dockerfile)  A copy of the dockerfile from [docker-getting-started-ap](https://GitHub.com/dstuartkelly/docker-getting-started-app) repository that was used in Part 1
    - [compose.yaml](./files/compose.yaml)  A copy of the docker compose file for  [docker-getting-started-ap](https://GitHub.com/dstuartkelly/docker-getting-started-app) repository used in Part 6

- [images](./images/) directory used to store various images displayed in each of the Part*.md documents