pam_rps
==========

## Instructions d'installation sous Centos 6.X+

### Prérequis

Avoir installé les prérequis de la page https://github.com/humboldtux/check_user

### Récupérez les sources

Clonez le dépôt

``` sh
$ cd
$ git clone https://github.com/humboldtux/pam_rps /tmp/pam_rps
```

### Compilation

``` sh
$ cd /tmp/pam_rps/src/
$ gcc -fPIC -c pam_rps.c
$ gcc -shared -o pam_rps.so pam_rps.o -lpam
```

### Installation

Un module `pam_rps` a été créé dans le dossier courant.
Vous pouvez copier dans le dossier des modules PAM de votre système:

``` sh
$ sudo mv pam_rps.so /lib64/security/
```

Ainsi que la page de manuel:

``` sh
$ gzip pam_rps.8.in -c | sudo tee /usr/share/man/man8/pam_rps.8.gz
$ man pam_rps
```

### Ménage

``` sh
$ cd
$ rm -rf /tmp/pam_rps
```
