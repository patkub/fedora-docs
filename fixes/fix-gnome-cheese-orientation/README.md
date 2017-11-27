---
title: Fix Gnome Cheese Orientation
layout: default
---

# fix-gnome-cheese-orientation

> change Gnome Cheese camera orientation

```sh
dnf install libv4l
```

Edit `/usr/share/applications/org.gnome.Cheese.desktop`. Launch cheese with a libv4l flag to control orientation. Set the `DBusActivatable` property to `false` to not ignore the `Exec` property.

```sh
Exec=bash -c "export LIBV4LCONTROL_FLAGS=1 && cheese"
DBusActivatable=false
```

# References

* [https://standards.freedesktop.org/desktop-entry-spec/desktop-entry-spec-latest.html](https://standards.freedesktop.org/desktop-entry-spec/desktop-entry-spec-latest.html)

