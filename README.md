# Deploy Discovering CS

These scripts are designed to allow you to run and manage an instance of 
the open-source [Discovering 
CS](https://github.com/daniel3735928559/discovering-cs) textbook.

## Serve the book statically

**Requires:**
* docker
* git
* bash
* Appropriate permissions to run docker commands

1. Clone this repository.  
2. In the directory of the cloned repo, run `./spinup 80 nohw`

This will start a server on port 80 serving the book statically.

## Serve the book with homework submission

**Requires:**
* docker
* git
* bash
* Appropriate permissions to run docker commands
* A setup in which some server is listening on port 80 and forwarding to 
port 61453 except for requests to anything inside /homework, which 
should be forwarded through some authentication server that sets the 
proxy-user HTTP header of the forwarded requests.'

1. Clone this repository.  
2. In the directory of the cloned repo, run `./spinup 61453`

## Resync the book to the git repository, ignoring homework backups

Run the same `spinup` command you used to start the server but with 
`nohw` as the second argument.  For example, 

`./spinup 61453 nohw`

Do this if you are not serving online homework or if there was no 
homework available for submission between now and the previous update.

## Resync the book to the git repository, backing up homework also

Run the same `spinup` command you used to start the server without 
`nohw` at the end.

## Make a backup of the homeworks, ratings, and/or logs

`./backup_hw`, `./backup_ratings`, `./backup_logs` respectively.
