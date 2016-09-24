This software is released under the MIT License, see LICENSE.txt.

[for English](https://github.com/yukihirai0505/centos-6.7-ansible/blob/master/README.md)

## About

CentOS6.7向けにAnsibleで

- PHP7
- Nginx
- MySQL5.6
- Java1.8
- Python3.5
- cron
- supervisor

などの設定を書いていく

## Get Started

このVagrantfileで作成したCentOS6.7向けに
環境構築していく

[https://github.com/yukihirai0505/centos-6.7-ansible/blob/master/Vagrantfile](https://github.com/yukihirai0505/centos-6.7-ansible/blob/master/Vagrantfile)

まだansibleを入れていない方は

`pip install ansible`

をしておきましょう。


`vagrant up` としたあとに

`vagrant ssh-config --host centos-6.7 >> ~/.ssh/config`

としてsshの設定をしていく。

**場合によってはprivate_keyを保存し直してあげる必要があるかもしれない。**

その場合は下記を試して見てください。

```
ssh-keygen -yf .vagrant/machines/default/virtualbox/private_key > public_key
cat public_key | pbcopy
```

としてCentOS6.7の `authorized_keys` ファイルを上書きしてあげて

`sudo chmod 600 ~/.ssh/authorized_keys` とすればひとまずsshの設定は問題ないはずです。


【参考】

- [Package化したboxを使うときによく出るエラー](http://blog.10rane.com/2015/08/28/errors-out-when-using-to-package-the-box/)
- [Vagrant vagrant upしたときに"Authentication failure. Retrying..."警告がでてvagrant sshできない状態からの脱出](http://qiita.com/jshimazu/items/9db49ce64478e82d511e)

sshの設定が完了したら下記のPATHにhostsファイルを作成。

`/etc/ansible/hosts`

```
[host]
centos-6.7
```

これで

`ansible-playbook development.yml`

でansibleを実行できるかと思います。