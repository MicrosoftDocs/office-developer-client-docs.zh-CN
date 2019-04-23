---
title: 最大限度地降低日志文件空间使用
TOCTitle: Minimizing log file space usage
ms:assetid: d527c313-35ad-c30e-6ea1-ddfeff1fe890
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250073(v=office.15)
ms:contentKeyID: 48547960
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: da4bf7c9c30d3b9b37e2835ddeeeab2b2ed8a2c6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288874"
---
# <a name="minimizing-log-file-space-usage"></a>最大限度地降低日志文件空间使用

**适用于**：Access 2013、Office 2013

如果 SQL Server 数据库上存在大量的活动，那么日志文件可能很快就会写满（从而阻碍服务器的运行）。您可以将日志文件设置为 **在检查点截断日志** ，以显著延长数据库日志文件的使用时间。

**在 Microsoft SQL Server 6.5 中启用"在检查点截断日志"功能的方法**

1.  启动 Microsoft SQL Server 企业管理器，打开"服务器"树，然后打开"数据库设备"树。

2.  双击要启用此功能的服务器的名称。

3.  From the **Database** tab, select **Truncate**.

4.  From the **Options** tab, select **Truncate Log on Checkpoint**, and then click **OK**.

**在 Microsoft SQL Server 7.0 中启用"在检查点截断日志"功能的方法**

1.  启动 Microsoft SQL Server 企业管理器，打开"服务器"树，然后打开"数据库"树。

2.  Right-click the name of the database on which this feature will be enabled and choose **Properties**.

3.  From the **Options** tab, select **Truncate Log on Checkpoint**, and then click **OK**.

有关 **在检查点截断日志** 功能的详细信息，请参阅 Microsoft SQL Server 文档。

