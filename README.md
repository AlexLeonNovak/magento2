# Initial magento 2 project
## Make with [markshust/docker-magento](https://github.com/markshust/docker-magento/tree/master)

### Instalation
Follow [this instruction](https://github.com/markshust/docker-magento/tree/master#setup) section **Existing Projects** but clone this repo
```bash
git clone https://github.com/AlexLeonNovak/magento2.git <project_name>

# Copy the env files from the example and configure it 
for file in env/*.env.example; do cp $file ${file/.example/}; done;

# If it first start follow next
bin/start --no-dev
bin/copytocontainer --all
bin/composer install ## if vendor dir is empty
bin/mysql < ../existing/magento.sql ## import db
# Create a DNS host entry and setup Magento base url
bin/setup-domain yoursite.test
bin/restart
open https://magento.test
# Or make install
bin/setup yoursite.test

# Next time, just do it
bin/start
```
