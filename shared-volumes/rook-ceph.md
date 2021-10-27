# Shared Volumes with rook/ceph

## General

  * cephfs arbeitet als Objectspeicher (RADOS)
  * Es wird eine Schnittstelle als Blockspeicher zur Verfügung gestellt
  * Ceph verwendet intern Monitoring - Server (MONs)
  * Um ceph in Kubernetes auszurollen sind MON's und OSDs notwendig

# RADOS

  * RADOS hat mehrere Komponenten 
  * Die Object Storage Daemons (OSDs) sind die Speichersilos in Ceph

## Ref: 

  * https://www.linux-magazin.de/ausgaben/2019/12/rook-2/4/
