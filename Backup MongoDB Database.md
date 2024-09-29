One way to backup a [[MongoDB]] database for free is to run a [[cron]] job with [[mongodump]] and restore the data with [[mongorestore]]. These are database tools provided by MongoDB

#### To install MongoDB Database Tools
```bash
brew tap mongodb/brew
brew install mongodb-database-tools
```

#### Note
`brew tap` adds repositories that [[Homebrew]] can track, update, and install from