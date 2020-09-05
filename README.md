# Relational database schema for [Raku](https://www.raku.org) language

[![Build Status](https://travis-ci.org/bbkr/DB_Schema.svg?branch=master)](https://travis-ci.org/bbkr/DB_Schema)

Represents structure of relational databases (MySQL, PostgreSQL).

Note:
* This is not Object Relational Mapper (like [RED](https://modules.raku.org/dist/Red:cpan:FCO) for example). You can not access data in tables using this module. However you may use it to discover database entities and quickly create ORM models if you like.
* This is not schema manager. You can not create databases, add tables or modify columns using this module. This may be added in the future.

# TABLE OF CONTENTS

* [SYNOPSIS](#synopsis)
* [METHODS](#methods)
* [CONTACT](#contact) 

# SYNOPSIS

```raku
use DB::Schema;

my $schema = DB::Schema.new(
    # auto-detect schema technology 
    connection => DBIish.connect( ... )
);

for $schema.databases -> $database {
    for $database.tables -> $table {
        for $table.columns -> $column {
            printf "Database %s has table %s with column %s\n",
                $database.name, $table.name, $column.name;
        }
    }
}
```

# METHODS

# CONTACT

You can find me on irc.freenode.net #raku channel as **bbkr**.
