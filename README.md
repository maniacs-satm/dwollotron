# Dwollotron
No, it's not ready for prime time. Dwollotron is an experiment to provide recurring payments on top of the Dwolla API. It is designed to identify needs in the Dwolla API to support these objectives, and shouldn't be considered ready-to-run code by any standards.

Dwollotron is a Rails 3.1 app with daemons for recurrence and the state_machine gem to provide finite states for transaction processing. It relies on Postgres for record locking.
##Prerequisites
* RVM
* ruby-1.9.3
* Postgres
* Redis

##Getting Started
1. Clone the repo.
1. Enter the directory, and allow RVM to create the new gemset.
1. Update your bundle with `bundle update`.
1. Copy config/database.example.yml to config/database.yml.
1. Create the database with `rake db:create` followed by `rake db:migrate`.
1. Launch the app with `foreman start`. The web application will run at http://localhost:5000, and both the queue processor and the scheduler will run.

##Making it Useful
Rewrite `app/models/payment.rb#call_remote_dwolla_api` to do something that actually calls an API to transfer money. That part's not done.

##Testing
For one-time testing, run `rspec`. For continual testing, run `autotest`.

##Miscellaneous
`git-up` is installed as a friendly alternative to `git pull --rebase`. `grb` is installed to help with remote branch management..