# Magento Docker Deploy

## REQUIREMENT

- DOCKER
- DOCKER-COMPOSE
- GIT
- mkcert

## START
- `git clone [URL]`
- mkcert setting domain [magento.test] and then put the *.pem file in the [image/nginx/certs] path
- localhost hosts add [127.0.0.1 magento.test] in the [etc/hosts] file

### STEP 1 : Download Magento2
`$ bin/download `

#### Description 
`Build the Container and Download the Magento2.4.3-p1`

### STEP 2 : Magento2 Setup Setting
`$ bin/setup`

#### Description
`Setup Magento2 Setting`

### SETP 3 : OPEN URL
`https://magento.test -> FrontEnd`

`https://magento.test/admin -> BackEnd`


## Folder

`bin => Sh Script`

`image => Docker Images`

`workspace => Magento2 Project`

## Notice (Sync Project <=> Container)
`use bin/copytocontainer to copy localhost workspace to container`

`use bin/copytocontainer to copy container to localhost workspace`