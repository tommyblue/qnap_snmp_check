# QnapSnmpCheck

A collection of Nagios/Icinga plugins to monitor QNAP devices via SNMP

## Requirements

It requires the *snmp* gem:

    gem install snmp

or, if you pulled the git repository including the Gemfile, just type:

    bundle install

## Installation

Copy the required plugins from the *plugins/* folder to the Nagios/Icinga plugins folder (e.g. _/usr/lib/nagios/plugins_) then add the check defines in the *commands.cfg* file:

    define command {
        command_name    qnap_snmp_check_raid
        command_line    $USER1$/qnap_snmp_check_raid -H $HOSTADDRESS$ -C public
    }

## Usage

TODO: Write usage instructions here

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
