# packer_tutorial_with_docker
Sample codes of Packer in HCL to work with Docker and File

### Init, Format and validate your Packer template
`packer init .`<br>
`packer fmt .`<br>
`packer validate .`

### Build Packer image
`packer build docker-ubuntu.pkr.hcl`

### Order of ascending precedence is: variable defaults, environment variables, variable file(s), command-line flag
`packer build --var-file=example.pkrvars.hcl docker-ubuntu.pkr.hcl`

### Packer will automatically load any variable file that matches the name *.auto.pkrvars.hcl, without the need to pass the file via the command line
`mv example.pkrvars.hcl example.auto.pkrvars.hcl`<br>
`packer build .`

### Build image with command line flag
`packer build --var docker_image=ubuntu:groovy .`

### Remove all Docker containers,images etc
`docker system prune -a`
