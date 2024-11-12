# Updating-CentOS---End-of-Life

CentOS reached its end of life on June 30, 2024, which will cause issues when attempting to download installation packages from repositories. The CentOS mirror list feature allows yum, the package manager, to automatically find and use the nearest and fastest mirror. To resolve this issue, you can mass update all .repo files with the following commands:

```
sed -i s/mirror.centos.org/vault.centos.org/g /etc/yum.repos.d/*.repo
sed -i s/^#.*baseurl=http/baseurl=http/g /etc/yum.repos.d/*.repo
sed -i s/^mirrorlist=http/#mirrorlist=http/g /etc/yum.repos.d/*.repo
yum clean all && yum -y update ```
