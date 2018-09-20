# Integration with permissions framework

Auditor portal is tightly connected with permissions framework. For their updating special management command were written. It can be called as

```text
python manage.py update_audit_permissions
```

and every time when called it collects required set of permissions, removes old permissions which are related to Audit \(their targets are starting with `audit.` or `purchase_order.`\) and creates everything that needed.

This command is very similar to the same in TPM module. For more info see related documentation:

{% embed data="{\"url\":\"https://razortheory.gitbook.io/third-party-monitoring-module-documentation/technical-documentation/permissions-framework\",\"type\":\"link\",\"title\":\"Permissions framework - Third Party Monitoring Module\",\"description\":\"etools.applications.permissions2\",\"icon\":{\"type\":\"icon\",\"url\":\"https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/spaces%2F-LJxGPxbbRc1mv-\_gOuP%2Favatar.png?generation=1535971137739491&alt=media\",\"aspectRatio\":0},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://www.gitbook.com/share/space/thumbnail/-LJxGPxbbRc1mv-\_gOuP.png\",\"width\":1200,\"height\":630,\"aspectRatio\":0.525}}" %}



