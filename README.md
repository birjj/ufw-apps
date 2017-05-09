# UFW Application Files

This is a repo of UFW application files. Use them to easily target specific applications when modifying your firewall.

## Installing

Clone the repo, copy (or symlink) the appropriate files to `/etc/ufw/applications.d/` and tell ufw to reload the config with `ufw app update <name>`:

```bash
git clone git@github.com:birjolaxew/ufw-apps.git
cd ufw-apps
for file in ufw-*; do
  app=${file#ufw-}
  sudo cp -i $file /etc/ufw/applications.d/
  sudo ufw app update $app
done
```

## Contributing

Pull requests are most welcome! Just make sure your files are named after the usual `ufw-<appname>` format, with one application per file.