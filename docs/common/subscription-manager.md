# subscription-manager

## References
* 

##### --help
```c
/*
Usage: subscription-manager MODULE-NAME [MODULE-OPTIONS] [--help]

Primary Modules:

  attach         Attach a specified subscription to the registered system
  list           List subscription and product information for this system
  refresh        Pull the latest subscription data from the server
  register       Register this system to the Customer Portal or another
                 subscription management service
  release        Configure which operating system release to use
  remove         Remove all or specific subscriptions from this system
  status         Show status information for this system's subscriptions and
                 products
  unregister     Unregister this system from the Customer Portal or another
                 subscription management service

Other Modules:

  auto-attach    Set if subscriptions are attached on a schedule (default of
                 daily)
  clean          Remove all local system and subscription data without affecting
                 the server
  config         List, set, or remove the configuration parameters in use by
                 this system
  environments   Display the environments available for a user
  facts          View or update the detected system information
  identity       Display the identity certificate for this system or request a
                 new one
  import         Import certificates which were provided outside of the tool
  orgs           Display the organizations against which a user can register a
                 system
  plugins        View and configure subscription-manager plugins
  redeem         Attempt to redeem a subscription for a preconfigured system
  repo-override  Manage custom content repository settings
  repos          List the repositories which this system is entitled to use
  service-level  Manage service levels for this system
  subscribe      Deprecated, see attach
  unsubscribe    Deprecated, see remove
  version        Print version information
*/
```
