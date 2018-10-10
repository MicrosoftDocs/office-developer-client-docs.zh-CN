---
title: 可重复读取隔离级别死锁
TOCTitle: Deadlocks With Read Repeatable Isolation Level
ms:assetid: 3d5f3293-33bb-cf6d-362a-278f9ec1bd3c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249165(v=office.15)
ms:contentKeyID: 48544342
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: de936da2772b809199d3890140683afd5ef01659
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466115"
---
# <a name="deadlocks-with-read-repeatable-isolation-level"></a>可重复读取隔离级别死锁


**适用于**： Access 2013 |Office 2013

如果自定义业务对象使用可重复读取隔离级别访问 SQL Server，且该业务对象同时被两个在相同事务中发送查询并进行更新的客户端调用，那么有可能发生死锁。远程数据服务专门设计为允许其中一个进程超时以释放死锁，但该客户端的更新将失败。

使用[游标服务](microsoft-cursor-service-for-ole-db-ado-service-component.md)**Command Time Out**动态属性来修改超时的长度。

