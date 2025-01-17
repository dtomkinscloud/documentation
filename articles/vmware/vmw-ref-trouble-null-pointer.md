---
title: Fixing your advanced gateway if you encounter NullPointerException error
description: Intended for customers who are experiencing the NullPointerException error when attempting to view their edge gateway properties
services: vmware
author: shighmoor
reviewer: jpaddock
lastreviewed: 16/07/2021
toc_rootlink: Reference
toc_sub1: 
toc_sub2:
toc_sub3:
toc_sub4:
toc_title: Fixing your advanced gateway if you encounter NullPointerException error
toc_fullpath: Reference/vmw-ref-trouble-null-pointer.md
toc_mdlink: vmw-ref-trouble-null-pointer.md
---

# Fixing your advanced gateway if you encounter NullPointerException error

With the upgrade to NSX version 6.4, edges that have been converted to an advanced gateway may produce an error when attempting to view the properties of the edge gateway in VMware Cloud Director. This does not affect access to the tenant portal GUI, where you can set up firewall rules and so on, this only affects viewing the edge properties such as the IP addresses assigned to an edge.

To complete the steps in this article, you must have access to VMware Cloud Director.

To fix your edge to enable viewing of its properties:

1. In the VMware Cloud Director *Virtual Data Center* dashboard, select the VDC that contains the broken edge.

2. In the left navigation panel, under *Networking*, select **Edges**.

    ![Edges menu option in VMware Cloud Director](images/vmw-vcd10.1-mnu-edges.png)

3. On the *Edge Gateways* page, select the edge that you want to configure and click **Services**.

    ![Services button](images/vmw-vcd10.1-edge-btn-services.png)

4. On the *Edge Gateway* page, select the **Routing** tab then the **Routing Configuration** tab.

5. In the *Static Routing Default Gateway* section, the **MTU** field will contain a value of `0`. Change the value from `0` to `1,500`.

6. When you're done, click **Save Changes** at the top of the page.

7. Close VMware Cloud Director and attempt to view the properties of the edge gateway in vCloud.

    You should no longer get the `NullPointerException` error and the properties should be displayed.

## Feedback

If you find a problem with this article, click **Improve this Doc** to make the change yourself or raise an [issue](https://github.com/UKCloud/documentation/issues) in GitHub. If you have an idea for how we could improve any of our services, send an email to <feedback@ukcloud.com>.
