
# Getting Started

Zooniverse classifications are stored in a Mongo database. To access raw classifications you need dumps from Mongo.  The two relevant collections are `spacewarps_subjects` and `spacewarps_classifications`.

  * `spacewarps_subjects` contains subjects and associated metadata, including the CFHTLS id.  Each subject has an id corresponding to an entry in the `spacewarps_classifications` collection
  * `spacewarps_classifications` contain all classifications that have been contributed by Zooniverse volunteers.

## Installation of Mongo

Visit the [Mongo website](http://www.mongodb.org/) for the binary installation.

## Restoring the Space Warps Database

Mongo comes with a nice command line utility to restore a database from a dump.  First request data from the Zooniverse development team.

    spacewarps-Y-m-d_H-M-S.tar.gz

Decompress it and run:
    
    # Spin up the mongo server, and provide a place for it to put stuff:
    mongod --dbpath . &
    
    # Load the database:
    mongorestore spacewarps-Y-m-d_H-M-S

Note: the server has to be running in the background for the mongo
python commands to run, but it still spits out stdout. So, it's best to
have the server running in a different terminal.

