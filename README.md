# Pigsty Repo

Supplementary packages for the [Pigsty](https://github.com/Vonng/pigsty) project:

- infra: prometheus & grafana stack, observability tools, distro-independent
- pgsql: PostgreSQL & EL related pkg, extensions and tools, distro-dependent

We have el7, el8, el9 repo for PostgreSQL 12 - 16, (16 is not available for el7)


```ini
[pigsty-pgsql]
name = Pigsty PGSQL $releasever - $basearch
baseurl = https://yum.pigsty.io/pgsql/el$releasever.$basearch
gpgcheck = 0
enabled = 1
module_hotfixes=1
```

To use this repo, adding this to your `/etc/yum.repos.d/pigsty-pgsql.repo`:

```bash
cat > /etc/yum.repos.d/pigsty-pgsql.repo <<-'EOF'
[pigsty-pgsql]
name = Pigsty PGSQL $releasever - $basearch
baseurl = https://yum.pigsty.io/pgsql/el$releasever.$basearch
gpgcheck = 0
enabled = 1
module_hotfixes=1
EOF
```

```bash
sudo curl https://yum.pigsty.io/pgsql/repo -o /etc/yum.repos.d/pigsty-pgsql.repo
```