OpenStack Aodh
##############

Ansible role that installs and configures OpenStack Aodh as the alarm
functionality of Telemetry.

This role will install the following:
    * aodh-api
    * aodh-listener
    * aodh-evaluator
    * aodh-notifier

The role will configure Aodh to use MongoDB for data storage, but does
not install or configure MongoDB.

Default Variables
=================

.. literalinclude:: ../../defaults/main.yml
   :language: yaml
   :start-after: under the License.

Example Playbook
================

.. code-block:: yaml

    - name: Install aodh services
      hosts: aodh_all
      user: root
      roles:
        - { role: "os_aodh", tags: [ "os-aodh" ] }
      vars:
        external_lb_vip_address: 172.16.24.1
        internal_lb_vip_address: 192.168.0.1
