# CRON
This repository contains Github action's workflow which runs via cron

1. [Digitalocean Backups](https://github.com/etienne-napoleone/goutte)
2. [Github To Gitea Backup](https://github.com/varunsridharan/github-gitea-mirror)

---

## Digitalocean Backups
DigitalOcean doesn't propose any way of automating snapshots. There are some SaaS that can take care of it but paying to execute some API requests seemed a bit off. That's why we developed a simple script which can run with cron jobs or in CI services like Travis for free. We use it daily to manage our backups.

It includes:

* Snapshoting droplets
* Snapshoting volumes
* Retention policy
* Pruning snapshots

---

## Github To Gitea Backup
### Why ?
What I’m trying to accomplish is a fail-safe in case something happens to GitHub which would make me loose access, be that voluntarily or involuntarily.

I am not migrating away from GitHub because I see no reason to: the platform is very useful to me, and I’d not like to loose it.

### Why Gitea

I’d like a Web UI onto these repositories in addition to the files in the file system. It could have been Gitlab, but I think Gitea is probably the option with the lowest resource requirements.

When I add a repository to Gitea and specify I want it to be mirrored, Gitea will take charge of periodically querying the source repository and pulling changes in it.