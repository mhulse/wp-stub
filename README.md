# WP Stub!

**Boilerplate code used to kick-start WordPress projects.**

This repo will eventually contain an updated version of my [Bueller repo/workflow](https://github.com/mhulse/bueller).

---

## Installation

### Automated

Using `cURL` and `tar` on a unix system:

```bash
# Create your WordPress site folder:
$ mkdir my-wordpress-site && cd my-wordpress-site
# Grab the relevant folders/files from this repo:
$ curl -#L https://github.com/mhulse/wp-stub/tarball/master | tar -xzv --strip-components 1 --exclude=*/{.git*,.editor*,README.*,LICENSE,*.sublime*}
# Grab and setup the latest WordPress:
$ wget http://wordpress.org/latest.tar.gz && tar xfz latest.tar.gz && rm -f latest.tar.gz && mv wordpress wp
```

Setup DB and tweak your settings. More info to come.

### Manually:

* Coming soon.
