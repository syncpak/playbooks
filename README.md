### SUMMARY WTI CPM module Ansible Playbook Examples

All WTI Ansible playbooks use Ansible native modules to communicate with WTI device. No programming knowledge is necessary but examining the output  from the easy to use playbooks might be more helpful if [you looked at the WTI RESTful documentation online](https://ftp.wti.com/pub/TechSupport/Restful_WTI/current/api/api.html "WTI RESTful API Documentation Page")

The `cpm_username` you use to log into the WTI device must have the proper "Access Level" and also have Service Access "RESTful API Access" turned on in the WTI device itself.
***

#### cpm_serial_ports
Works with the WTI cpm_serial_ports module included in Ansible 2.9 (and above) to get/set serial port settings of WTI OOB and PDU devices. The `get` requires SuperUser "Access Level", while the `add` and `edit` require Administrator "Access Level"

**port_info.yml:** Gets various user parameters defined to the `"port"` variable.

**port_config.yml:** Modifies parameters of the defined `"port"` variable.

#### cpm_plugcontrol
Works with the WTI cpm_plugcontrol module included in Ansible 2.8 (and above) to get/control plugs of WTI PDU devices. The `get` requires SuperUser "Access Level", while the `set` require Administrator "Access Level"

**plugget.yml:** Gets various real time plug state numbers defined to the `"plug_id"` variable.

**plugset.yml:** Set the plug state of the defined `"plug_id"` variable.

#### cpm_plugconfig
Works with the WTI cpm_plugconfig module included in Ansible 2.8 (and above) to get/configure plugs of WTI PDU devices. The `get` requires SuperUser "Access Level", while the `set` require Administrator "Access Level"

**plugget.yml:** Gets various plug parameters defined to the `"plug_id"` variable.

**plugset.yml:** Set the plug state of the defined `"plug_id"` variable.

#### cpm_status
Works with the WTI cmp_status lookup plugin included in Ansible 2.7 (and above) to get various configuration/real-time operating statistics of WTI OOB and PDU devices.

**getverlookup.yml:** Get the firmware version of the WTI device

**gettemplookup.yml:** Get the current working temperature of the WTI device, report in either Fahrenheit or Celsius depending how the device is configured.

**getstatuslookup.yml:** Gets various operating parameters of the WTI device, such as macaddresses, web version, SSH version, openssl version, product tag, etc.

**getalarmslookup.yml:** Gets the alarm names and real time status of any unusual conditions of the unit, for example Over current, Over temperature, Ping No Answer, Lost communication, etc.
***
#### cpm_metering
Works with the WTI cmp_metering lookup plugs included in Ansible 2.7 (and above) to get realtime and historical power and current reading from WTI power type devices.

**currentgetlookup.yml:** If no parameters are passed, this will return the real-time current consumption along with plug count and various power capability reporting statistics. If `startdate` and `enddate` are defined in the playbook a historical listing of current consumption will be returned.

**powergetlookup.yml:** If no parameters are passed, this will return the real-time power consumption along with plug count and various power capability reporting statistics. If `startdate` and `enddate` are defined in the playbook a historical listing of current power will be returned.
***
#### cpm_user
Works with the WTI cmp_user module included in Ansible 2.7 (and above) to get/set user settings of WTI OOB and PDU devices. The `get` requires SuperUser "Access Level", while the `add`, `edit` and `delete` require Administrator "Access Level"

**userget.yml:** Gets various user parameters defined to the `"user_name"`  account.

**useradd.yml:** Add a New user defined as `"user_name"`.

**useredit.yml:** Edits an Existing user defined as `"user_name"`, if a parameter is not defined then it will remained as it did before this edit.

**userdelete.yml:** Deletes the user `"user_name"` from the WTI device.

### NOTES
cpm_interface, cpm_time_date are currently in review and are not included with the release Ansible 2.9.x
