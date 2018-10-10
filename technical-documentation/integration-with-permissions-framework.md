# Integration with permissions framework

Auditor portal is tightly connected with the permissions framework. Special management command were written to update them. It can be called as:

```text
python manage.py update_audit_permissions
```

and every time when called it collects required set of permissions, removes old permissions which are related to Audit \(their targets are starting with `audit.` or `purchase_order.`\) and creates everything that needed.

This command is very similar to the same in TPM module. For more info see related documentation:

{% embed url="https://razortheory.gitbook.io/third-party-monitoring-module-documentation/technical-documentation/permissions-framework" %}



