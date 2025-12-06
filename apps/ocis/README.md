# ocis

ownCloud Infinite Scale (oCIS) is the new file sync & share platform that will be the foundation of your data management platform from ownCloud GmbH.

source: [GitHub](https://github.com/owncloud/ocis)

## Opinion

The new project oCIS is really good, and for me, it’s miles better than Nextcloud or the previous ownCloud application. I tested the integration with OnlyOffice, Tika, and ClamAV, and it works without any issues.

The worst thing about this tool is configuration and operation. To understand and configure it properly, you need to go through the rather awful documentation of oCIS, and let’s not even start talking about the oCIS Helm chart: [ocis-charts](https://github.com/owncloud/ocis-charts).

At first, I thought this would be a game-changer for self-hosted enthusiasts with an overkill Kubernetes setup. However, the Helm chart updates can be frustrating and are mainly targeted at large environments with an LDAP backend. In my homelab, I will never install an OpenLDAP service—except for testing or learning purposes.
