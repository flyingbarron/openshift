---

copyright:
  years: 2014, 2019
lastupdated: "2019-08-19"

keywords: openshift, roks, rhoks, rhos

subcollection: openshift

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:codeblock: .codeblock}
{:tip: .tip}
{:note: .note}
{:download: .download}
{:preview: .preview}
{:external: target="_blank" .external}

# Version changelog
{: #openshift_changelog}

View information of version changes for major, minor, and patch updates that are available for your {{site.data.keyword.openshiftlong}} clusters. Changes include updates to OpenShift, Kubernetes, and {{site.data.keyword.cloud_notm}} Provider components.
{:shortdesc}

Unless otherwise noted in the changelogs, the {{site.data.keyword.containerlong_notm}} provider version enables Kubernetes APIs and features that are at beta. Kubernetes alpha features, which are subject to change, are disabled.

Check the [Security Bulletins on {{site.data.keyword.cloud_notm}} Status](https://cloud.ibm.com/status?selected=security) for security vulnerabilities that affect Red Hat OpenShift on IBM Cloud. You can filter the results to view only **Kubernetes Cluster** security bulletins that are relevant to Red Hat OpenShift on IBM Cloud. Changelog entries that address other security vulnerabilities but do not also refer to an IBM security bulletin are for vulnerabilities that are not known to affect Red Hat OpenShift on IBM Cloud in normal usage. If you run privileged containers, run commands on the workers, or execute untrusted code, then you might be at risk.

Master patch updates are applied automatically. Worker node patch updates can be applied by reloading or updating the worker nodes. For more information about major, minor, and patch versions and preparation actions between minor versions, see [OpenShift versions](/docs/containers?topic=containers-cs_versions).
{: tip}

## Version 3.11 changelog

Review the changelogs for Red Hat OpenShift on IBM Cloud version 3.11 patch updates.
{: shortdesc}

### Changelog for worker node fix pack 3.11.135_1521_openshift, released 19 August 2019
{: #311135_1521_worker}

The following table shows the changes that are included in the worker node fix pack `3.11.135_1521_openshift`.
{: shortdesc}

| Component | Previous | Current | Description |
| --------- | -------- | ------- | ----------- |
| Cluster master HA proxy | 2.0.1-alpine | 1.8.21-alpine | Moved to HA proxy 1.8 to fix [socket leak in haproxy](https://github.com/haproxy/haproxy/issues/136){: external}. Added a livliness check to monitor the health of HA proxy. For more information about other changes, see [release notes](https://www.haproxy.org/download/1.8/src/CHANGELOG){: external}. |
| OpenShift node | 3.11.129 | 3.11.135 | For more information, see the [OpenShift release notes](https://docs.openshift.com/container-platform/3.11/release_notes/ocp_3_11_release_notes.html#ocp-3-11-135){: external}. |
| RHEL 7 kernel | 3.10.0-957.21.3.el7 | 3.10.0-1062.el7 | Updated worker node images with kernel and package updates for [CVE-2018-16881](https://nvd.nist.gov/vuln/detail/CVE-2018-168810){: external}, [CVE-2019-6470](https://nvd.nist.gov/vuln/detail/CVE-2019-6470){: external}, [CVE-2018-14618](https://nvd.nist.gov/vuln/detail/CVE-2018-14618){: external}, [CVE-2018-16062](https://nvd.nist.gov/vuln/detail/CVE-2018-16062){: external}, [CVE-2018-16402](https://nvd.nist.gov/vuln/detail/CVE-2018-16402){: external}, [CVE-2018-16403](https://nvd.nist.gov/vuln/detail/CVE-2018-16403){: external}, [CVE-2018-18310](https://nvd.nist.gov/vuln/detail/CVE-2018-18310){: external}, [CVE-2018-18520](https://nvd.nist.gov/vuln/detail/CVE-2018-18520){: external}, [CVE-2018-18521](https://nvd.nist.gov/vuln/detail/CVE-2018-18521){: external}, [CVE-2019-7149](https://nvd.nist.gov/vuln/detail/CVE-2019-7149){: external}, [CVE-2019-7150](https://nvd.nist.gov/vuln/detail/CVE-2019-7150){: external}, [CVE-2019-7664](https://nvd.nist.gov/vuln/detail/CVE-2019-7664){: external}, [CVE-2019-7665](https://nvd.nist.gov/vuln/detail/CVE-2019-7665){: external}, [CVE-2016-10739](https://nvd.nist.gov/vuln/detail/CVE-2016-10739){: external}, [CVE-2018-16871](https://nvd.nist.gov/vuln/detail/CVE-2018-16871){: external}, [CVE-2018-16884](https://nvd.nist.gov/vuln/detail/CVE-2018-16884){: external}, [CVE-2019-11085](https://nvd.nist.gov/vuln/detail/CVE-2019-11085){: external}, [CVE-2019-11811](https://nvd.nist.gov/vuln/detail/CVE-2019-11811){: external}, [CVE-2018-15686](https://nvd.nist.gov/vuln/detail/CVE-2018-15686){: external}, [CVE-2018-16866](https://nvd.nist.gov/vuln/detail/CVE-2018-16866){: external}, [CVE-2018-16888](https://nvd.nist.gov/vuln/detail/CVE-2018-16888){: external}, [CVE-2018-12327](https://nvd.nist.gov/vuln/detail/CVE-2018-12327){: external}, [CVE-2018-12641](https://nvd.nist.gov/vuln/detail/CVE-2018-12641){: external}, [CVE-2018-12697](https://nvd.nist.gov/vuln/detail/CVE-2018-12697){: external}, [CVE-2018-1000876](https://nvd.nist.gov/vuln/detail/CVE-2018-1000876){: external}, [CVE-2018-16842](https://nvd.nist.gov/vuln/detail/CVE-2018-16842){: external}, [CVE-2018-5741](https://nvd.nist.gov/vuln/detail/CVE-2018-5741){: external}, [CVE-2018-0495](https://nvd.nist.gov/vuln/detail/CVE-2018-0495){: external}, [CVE-2018-12404](https://nvd.nist.gov/vuln/detail/CVE-2018-12404){: external}, [CVE-2018-1122](https://nvd.nist.gov/vuln/detail/CVE-2018-1122){: external}, [CVE-2018-7755](https://nvd.nist.gov/vuln/detail/CVE-2018-7755){: external}, [CVE-2018-8087](https://nvd.nist.gov/vuln/detail/CVE-2018-8087){: external}, [CVE-2018-9363](https://nvd.nist.gov/vuln/detail/CVE-2018-9363){: external}, [CVE-2018-9516](https://nvd.nist.gov/vuln/detail/CVE-2018-9516){: external}, [CVE-2018-9517](https://nvd.nist.gov/vuln/detail/CVE-2018-9517){: external}, [CVE-2018-10853](https://nvd.nist.gov/vuln/detail/CVE-2018-10853){: external}, [CVE-2018-13053](https://nvd.nist.gov/vuln/detail/CVE-2018-13053){: external}, [CVE-2018-13093](https://nvd.nist.gov/vuln/detail/CVE-2018-13093){: external}, [CVE-2018-13094](https://nvd.nist.gov/vuln/detail/CVE-2018-13094){: external}, [CVE-2018-13095](https://nvd.nist.gov/vuln/detail/CVE-2018-13095){: external}, [CVE-2018-14625](https://nvd.nist.gov/vuln/detail/CVE-2018-14625){: external}, [CVE-2018-14734](https://nvd.nist.gov/vuln/detail/CVE-2018-14734){: external}, [CVE-2018-15594](https://nvd.nist.gov/vuln/detail/CVE-2018-15594){: external}, [CVE-2018-16658](https://nvd.nist.gov/vuln/detail/CVE-2018-16658){: external}, [CVE-2018-16885](https://nvd.nist.gov/vuln/detail/CVE-2018-16885){: external}, [CVE-2018-18281](https://nvd.nist.gov/vuln/detail/CVE-2018-18281){: external}, [CVE-2019-3459](https://nvd.nist.gov/vuln/detail/CVE-2019-3459){: external}, [CVE-2019-3460](https://nvd.nist.gov/vuln/detail/CVE-2019-3460){: external}, [CVE-2019-3882](https://nvd.nist.gov/vuln/detail/CVE-2019-3882){: external}, [CVE-2019-3900](https://nvd.nist.gov/vuln/detail/CVE-2019-3900){: external}, [CVE-2019-5489](https://nvd.nist.gov/vuln/detail/CVE-2019-5489){: external}, [CVE-2018-18074](https://nvd.nist.gov/vuln/detail/CVE-2018-18074){: external}, [CVE-2019-3858](https://nvd.nist.gov/vuln/detail/CVE-2019-3858){: external}, [CVE-2019-3861](https://nvd.nist.gov/vuln/detail/CVE-2019-3861){: external}, [CVE-2019-3862](https://nvd.nist.gov/vuln/detail/CVE-2019-3862){: external}, [CVE-2018-14647](https://nvd.nist.gov/vuln/detail/CVE-2018-14647){: external}, [CVE-2019-5010](https://nvd.nist.gov/vuln/detail/CVE-2019-5010){: external}, [CVE-2019-9740](https://nvd.nist.gov/vuln/detail/CVE-2019-9740){: external}, [CVE-2019-9947](https://nvd.nist.gov/vuln/detail/CVE-2019-9947){: external}, [CVE-2019-9948](https://nvd.nist.gov/vuln/detail/CVE-2019-9948){: external}, [CVE-2017-14503](https://nvd.nist.gov/vuln/detail/CVE-2017-14503){: external}, [CVE-2018-1000877](https://nvd.nist.gov/vuln/detail/CVE-2018-1000877){: external}, [CVE-2018-1000878](https://nvd.nist.gov/vuln/detail/CVE-2018-1000878){: external}, [CVE-2019-1000019](https://nvd.nist.gov/vuln/detail/CVE-2019-1000019){: external}, [CVE-2019-1000020](https://nvd.nist.gov/vuln/detail/CVE-2019-1000020){: external}, [CVE-2018-3058](https://nvd.nist.gov/vuln/detail/CVE-2018-3058){: external}, [CVE-2018-3063](https://nvd.nist.gov/vuln/detail/CVE-2018-3063){: external}, [CVE-2018-3066](https://nvd.nist.gov/vuln/detail/CVE-2018-3066){: external}, [CVE-2018-3081](https://nvd.nist.gov/vuln/detail/CVE-2018-3081){: external}, [CVE-2018-3282](https://nvd.nist.gov/vuln/detail/CVE-2018-3282){: external}, [CVE-2019-2503](https://nvd.nist.gov/vuln/detail/CVE-2019-2503){: external}, [CVE-2019-2529](https://nvd.nist.gov/vuln/detail/CVE-2019-2529){: external}, [CVE-2019-2614](https://nvd.nist.gov/vuln/detail/CVE-2019-2614){: external}, [CVE-2019-2627](https://nvd.nist.gov/vuln/detail/CVE-2019-2627){: external}, [CVE-2018-14348](https://nvd.nist.gov/vuln/detail/CVE-2018-14348){: external}, [CVE-2018-15473](https://nvd.nist.gov/vuln/detail/CVE-2018-15473){: external}, [CVE-2018-5383](https://nvd.nist.gov/vuln/detail/CVE-2018-5383){: external}, [CVE-2018-19788](https://nvd.nist.gov/vuln/detail/CVE-2018-19788){: external}, [CVE-2018-0734](https://nvd.nist.gov/vuln/detail/CVE-2018-0734){: external}, [CVE-2019-1559](https://nvd.nist.gov/vuln/detail/CVE-2019-1559){: external}, [CVE-2018-20060](https://nvd.nist.gov/vuln/detail/CVE-2018-20060){: external}, and [CVE-2019-11236](https://nvd.nist.gov/vuln/detail/CVE-2019-11236){: external}. |
{: caption="Changes since version 3.11.129_1518" caption-side="top"}

### Changelog for master fix pack 3.11.135_1521_openshift, released 17 August 2019
{: #311135_1521_master}

The following table shows the changes that are included in the master fix pack `3.11.135_1521_openshift`.
{: shortdesc}

| Component | Previous | Current | Description |
| --------- | -------- | ------- | ----------- |
| Key Management Service provider | 167 | 207 | Fixed an issue that causes the Kubernetes key management service (KMS) provider to fail to manage Kubernetes secrets. |
{: caption="Changes since version 3.11.135_1520" caption-side="top"}

### Changelog for master fix pack 3.11.135_1520_openshift, released 15 August 2019
{: #311135_1520_master}

The following table shows the changes that are included in the master fix pack `3.11.135_1520_openshift`.
{: shortdesc}

| Component | Previous | Current | Description |
| --------- | -------- | ------- | ----------- |
| Calico configuration | N/A | N/A | Calico `calico-kube-controllers` deployment in the `kube-system` namespace sets a memory limit on the `calico-kube-controllers` container. |
| {{site.data.keyword.cloud_notm}} Block Storage driver and plug-in | 1.15 | 1.15.1 | Image updated for [CVE-2019-14697](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-14697){: external}. |
| {{site.data.keyword.cloud_notm}} File Storage plug-in | 347 | 348 | Image updated for [CVE-2019-14697](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-14697){: external}. |
| Load balancer and load balancer monitor for {{site.data.keyword.cloud_notm}} Provider | 146 | 147 | Image updated for [CVE-2019-14697](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-14697){: external}. |
| OpenShift | 3.11.129 | 3.11.135 | See the [OpenShift release notes](https://docs.openshift.com/container-platform/3.11/release_notes/ocp_3_11_release_notes.html#ocp-3-11-135){: external}. |
| OpenVPN client | 2.4.6-r3-IKS-90 | 2.4.6-r3-IKS-116 | Image updated for [CVE-2019-14697](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-14697){: external}. |
{: caption="Changes since version 3.11.129_1517" caption-side="top"}

### Changelog for worker node patch 3.11.129_1518_openshift, released 5 August 2019
{: #311129_1518_worker}

The following table shows the changes that are included in the worker node patch `3.11.129_1518_openshift`.
{: shortdesc}

| Component | Previous | Current | Description |
| --------- | -------- | ------- | ----------- |
| RHEL 7 packages | N/A | N/A | Updated base packages in the worker node Red Hat Enterprise Linux image. |
{: caption="Changes since version 3.11.129_1517" caption-side="top"}

### Changelog for 3.11.129_1517_openshift, released 2 August 2019
{: #311129_1517}

The following table shows the changes that are included in the patch `3.11.129_1517_openshift`.
{: shortdesc}

| Component | Previous | Current | Description |
| --------- | -------- | ------- | ----------- |
| Cluster DNS configuration| N/A | N/A | For security reasons, enhanced local `dnsmasq` cache to listen on only `localhost`. Changed the DNS `targetPort` for the `kubernetes` cluster service from `8053` to `53`. |
| Cluster master HA proxy| 1.9.7-alpine| 2.0.1-alpine | See the [HAProxy release notes](https://www.haproxy.org/download/2.0/src/CHANGELOG){: external}. |
| Cluster router configuration| N/A | N/A | Fixed bugs that might cause cluster master operations, such as `refresh` or `update`, to fail when the router configuration is updated. These fixes also improve master availability during such operations. |
{: caption="Changes since version 3.11.129_1515" caption-side="top"}