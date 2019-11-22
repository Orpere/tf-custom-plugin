# tf-custom-plugin
tf - custom plugin
vagrant project with golang installed

- [x] Setup a Vagrantfile that installs golang

```bash
vagrant up
```

- [x] Compile a custom plugin

```bash
vagrant ssh
go get github.com/petems/terraform-provider-extip
cd ~/go/src/github.com/petems/terraform-provider-extip
make build
ls -al ~/go/bin/
```

- [x] Copy the custom plugin to the required path

```bash
ln -s $GOPATH/bin/terraform-provider-extip ~/.terraform.d/plugins/
mkdir -p /vagrant/terraform.d/plugins/linux_amd64
cp ~/go/bin/terraform-provider-extip /vagrant/terraform.d/plugins/linux_amd64/
```

- [x] Test it works.

```bash
cd /vagrant
terraform apply
```

- [x] clean the vagrant machine

```bash
exit
vagrant destroy 
```
