A simple module adding the required rules to allow access can be generated from log files using audit2allow with following steps:

Set the daemon's domain (security context) to permissive mode. In permissive mode the policy isn't enforced, but logs are generated on the access the policy would normally deny.

semanage permissive -a <domain>
Test your daemon in normal operation to generate log entries.

Create a new policy module and insert it.

audit2allow -a -M <name>
semodule -i <name>.pp'
Re-enable enforcing mode

semanage permissive -d <domain>
This method works best when there are only a few security contexts involved. In a complex configuration you quite likely have to write your own policy module. Some resources for getting started are gentoo wiki and the reference policy API documentation.
