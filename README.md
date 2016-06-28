ansible-geoip
=============
[![Build Status](https://travis-ci.org/CyVerse-Ansible/ansible-geoip.svg?branch=master)](https://travis-ci.org/CyVerse-Ansible/ansible-geoip)

Installs the [GeoLiteCity database](https://dev.maxmind.com/geoip/legacy/geolite/).

This role is idempotent, and can safely be used as a dependency for other roles which use the
GeoIP database. Primary examples are roles which install [Packetbeat](https://www.elastic.co/guide/en/beats/packetbeat/current/configuration-shipper.html#_geoip_paths) or [Logstash](https://www.elastic.co/guide/en/logstash/current/plugins-filters-geoip.html#plugins-filters-geoip-database).


Requirements
------------

Only supports linux based operating systems.

Role Variables
--------------

|   Variable      | required | default             | choices                         | comments                                               |
|-----------------|----------|---------------------|---------------------------------|--------------------------------------------------------|
| geo_ip_folder   |  no      | "/usr/share/GeoIP"  | Valid filesystem directory path | The location where the GeoIP databases will be extracted. |
| geo_ip_override |  no      | false               | true/false                      | When true, will force update the GeoIP database file, overriding the original. |

Dependencies
------------

N/A

Example Playbook
----------------


    - hosts: servers
      roles:
         - role: ansible-geoip 

    - hosts: servers
      roles:
         - role: ansible-geoip 
           geo_ip_override: true
License
-------

BSD

Author Information
------------------

Jonathan Strootman - jstroot@cyverse.org

