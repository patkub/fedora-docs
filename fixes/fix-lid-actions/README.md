# fix-lid-actions

Opening / closing laptop lid sends scancodes which correspond to GNOME's Airplane Mode On. Fix this by mapping the scancodes to keycode 245 (Display Off).

Use `{ journalctl -f }` before closing and opening your lid to find out if closing the lid simulates any key presses. The journal entry should also tell you the scan code of the key press (e058 & e057 in my case)

Then use `{ setkeycodes [SCANCODE] [KEYCODE] }` to map the scancode sent by the lid to a desired key. Use `setkeycodes e058 245 e057 245` to map it to `DISPLAY OFF` or use a different keycode from the list in `/usr/include/linux/input-event-codes.h`

If the problem is fixed make it persistent by creating and enabling a systemd unit file in `/etc/systemd/system/`. See [fix-lid-actions.service](fix-lid-actions.service).

# References

* [https://www.reddit.com/r/archlinux/comments/62lk65/arch_gnome_stopped_suspend_now_how_do_i_prevent/dfusd9e/](https://www.reddit.com/r/archlinux/comments/62lk65/arch_gnome_stopped_suspend_now_how_do_i_prevent/dfusd9e/)

