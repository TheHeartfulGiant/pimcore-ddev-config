# Pimcore X DDEV

Uses DDEV for local pimcore development with nginx, redis and mutagen. Tested on M1 MacBook Pro.

## Setup

```bash
# 1. Clone this Project

# 2. Delete .git directory

# 3. Rename you Project in ./.ddev/config.yaml

# 4. Run ddev config - enter on all questions
ddev config

# 5. Start DDEV
ddev start

# 6. Create Pimcore Project using composer
ddev composer create pimcore/skeleton

# 7. Sometimes DDEV DB has initial no utf8mb4 charset configurated.
#    this fixes the Problem. If you can not run this, log into you
#    with ddev ssh and run it there without ddev.
ddev mysql -e "DROP DATABASE db; CREATE DATABASE db;"
ddev mysql -e "DROP DATABASE test; CREATE DATABASE test;"

# 8. Run Pimcore install
ddev pimcore-install

# DONE!
```

## Pimcore Commands

Often you use bin/console in your Pimcore Project. Todo so in DDEV use:

```bash
ddev pimcore <COMMAND> <ARGS>
# example
ddev pimcore cache:clear --no-warmup
```

## Credits

[DDEV](https://ddev.com/)  
[DDEV Documentaion](https://ddev.readthedocs.io/)  
[Pimcore Github](https://github.com/pimcore/pimcore)  
[Pimcore](https://pimcore.com)  
[Docker](https://www.docker.com/)  