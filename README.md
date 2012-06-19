# QnapSnmpCheck

A collection of Nagios/Icinga plugins to monitor QNAP devices via SNMP

## Requirements

It requires the *snmp* gem:

    gem install snmp

or, if you pulled the git repository including the Gemfile, just type:

    bundle install

This plugin was successfully tested with TS-410 and probably only works for it (or other 4-disks QNAPs), but the code is simple so just patch it :)

## Installation

Copy **check_qnap** plugin into the Nagios/Icinga plugins folder (e.g. _/usr/lib/nagios/plugins_) then add the check define in the *commands.cfg* file:

    define command {
        command_name    check_qnap
        command_line    $USER1$/check_qnap -H $HOSTADDRESS$ -c $ARG1$
    }

## Usage

Add desired service checks to a QNAP host:

    define service{
          use                             generic-service
          host_name                       qnap_host
          service_description             Disks
          check_command                   check_qnap!check_global_smart
    }

    define service{
          use                             generic-service
          host_name                       qnap_host
          service_description             Temperatures
          check_command                   check_qnap!check_global_temp
    }

**check_global_temp** returns performance data too.
You can perform also single checks, the complete list is in the code, check the **COMMANDS** hash.

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
