# SMTP Mail #

This plugin reconfigures the wp_mail() function to use SMTP instead of mail() and creates an options page that allows you to specify various options.

You can set the following options:

* Specify the from name and email address for outgoing email.
* Choose to send mail by SMTP or PHP's mail() function.
* Specify an SMTP host (defaults to localhost).
* Specify an SMTP port (defaults to 25).
* Choose SSL / TLS encryption (not the same as STARTTLS).
* Choose to use SMTP authentication or not (defaults to not).
* Specify an SMTP username and password.

## Installation ##

1. Download
2. Upload to your `/wp-contents/plugins/` directory.
3. Activate the plugin through the 'Plugins' menu in WordPress.

## Frequently Asked Questions ##

### My plugin still sends mail via the mail() function ###

If other plugins you're using are not coded to use the wp_mail() function but instead call PHP's mail() function directly, they will bypass the settings of this plugin. Normally, you can edit the other plugins and simply replace the `mail(` calls with `wp_mail(` (just adding wp_ in front) and this will work. I've tested this on a couple of plugins and it works, but it may not work on all plugins.

### Will this plugin work with WordPress versions less than 2.7? ###

No. WordPress 2.7 changed the way options were updated, so the options page will only work on 2.7 or later.

### Can I use this plugin to send email via Gmail / Google Apps ###

Yes. Use these settings:
* Mailer: **SMTP**
* SMTP Host: **smtp.gmail.com**
* SMTP Port: **465**
* Encryption: **SSL**
* Authentication: **Yes**
* Username: **(your full gmail address)**
* Password: **(your mail password)**

### Can you add feature x, y or z to the plugin? ###

Short answer: maybe.

By all means please contact me to discuss features or options you'd like to see added to the plugin. I can't guarantee to add all of them, but I will consider all sensible requests. I can be contacted here:
<http://www.callum-macdonald.com/code/wp-mail-smtp/>

## Changelog ##
### Version: 0.9.1 ###

* $phpmailer->language became protected in WP 3.2, no longer unset on debug output.

### Version: 0.9.0 ###

* Typo in the From email description.
* Removed changelog from plugin file, no need to duplicate it.
* Optionally set $phpmailer->Sender from from email, helps with sendmail / mail().

### Version: 0.8.7 ###

* Fix for a long standing bug that caused an error during plugin activation.

### Version: 0.8.6 ###

* The Settings link really does work this time, promise. Apologies for the unnecessary updates.

### Version: 0.8.5 ###

* Bugfix, the settings link on the Plugin page was broken by 0.8.4.

### Version: 0.8.4 ###

* Minor bugfix, remove use of esc_html() to improve backwards compatibility.
* Removed second options page menu props ovidiu.

### Version: 0.8.3 ###

* Bugfix, return WPMS_MAIL_FROM_NAME, props nacin.
* Add Settings link, props Mike Challis http://profiles.wordpress.org/MikeChallis/

### Version: 0.8.2 ###

* Bugfix, call phpmailer_init_smtp() correctly, props Sinklar.

### Version: 0.8.1 ###

* Internationalisation improvements.

### Version: 0.8 ###

* Added port, SSL/TLS, option whitelisting, validate_email(), and constant options.

### Version: 0.7 ###

* Added checks to only override the default from name / email

### Version: 0.6 ###

* Added additional SMTP debugging output

### Version: 0.5.2 ###

* Fixed a pre 2.3 bug to do with mail from

### Version: 0.5.1 ###

* Added a check to display a warning on versions prior to 2.3

### Version: 0.5.0 ###

* Upgraded to match 2.3 filters which add a second filter for from name

### Version: 0.4.2 ###

* Fixed a bug in 0.4.1 and added more debugging output

### Version: 0.4.1 ###

* Added $phpmailer->ErroInfo to the test mail output

### Version: 0.4 ###

* Added the test email feature and cleaned up some other bits and pieces

### Version: 0.3.2 ###

* Changed to use register_activation_hook for greater compatability

### Version: 0.3.1 ###

* Added readme for WP-Plugins.org compatability

### Version: 0.3 ###

* Various bugfixes and added From options

### Version: 0.2 ###

* Reworked approach as suggested by westi, added options page

### Version: 0.1 ###

* Initial approach, copying the wp_mail function and replacing it

### Version: 0.9.1 ###

Test mail functionality was broken on upgrade to 3.2, now restored.

### Version: 0.9.0 ###

Low priority upgrade. Improves the appearance of the options page.

### Version: 0.8.7 ###

Very low priority update. Fixes a bug that causes a spurious error during activation.

### Version: 0.8.6 ###

Low priority update. The Settings link was still broken in 0.8.5.

### Version: 0.8.5 ###

Minor bugfix correcting the Settings link bug introduced in 0.8.4. Very low priority update.

### Version: 0.8.4 ###

Minor bugfix for users using constants. Another very low priority upgrade. Apologies for the version creep.

### Version: 0.8.3 ###

Minor bugfix for users using constants. Very low priority upgrade.

## License
This software is free software; you may redistribute it and/or modify it under the terms of the GNU General Public License version 2 as published by the Free Software Foundation (http://www.fsf.org/).

                  GNU GENERAL PUBLIC LICENSE
                     Version 2, June 1991
    
    Copyright (C) 2012 Matt Rude <matt@mattrude.com>
    Copyright (C) 2011 Callum Macdonald <bl@callum-macdonald.com>

    This program is free software; you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation; either version 2 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License along
    with this program; if not, write to the Free Software Foundation, Inc.,
    51 Franklin Street, Fifth Floor, Boston, MA 02110-1301 USA.
