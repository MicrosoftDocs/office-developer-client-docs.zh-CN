---
title: XML Recordset 持久化方案
TOCTitle: XML Recordset Persistence Scenario
ms:assetid: 08f464da-10ba-b649-7571-766a40da2e04
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248825(v=office.15)
ms:contentKeyID: 48543107
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 378d3b1fc559cc07c1eb3a58621a8a4bd09a06ab
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25861820"
---
# <a name="xml-recordset-persistence-scenario"></a>XML 记录集暂留方案

**适用于**： Access 2013 |Office 2013

## <a name="xml-recordset-persistence-scenario"></a>XML 记录集暂留方案

在该方案中，您将创建一个 Active Server Pages (ASP) 应用程序，该应用程序将 **Recordset** 对象的内容直接保存到 ASP **Response** 对象中。

> [!NOTE]
> [!注释] 该方案要求您的服务器上装有 Internet Information Server 5.0 (IIS) 或更高版本。

返回的 **Recordset** 使用 [RDS.DataControl](datacontrol-object-rds.md) 显示在 Internet Explorer 中。

下列步骤是创建该方案所必需的步骤：

1.  设置应用程序。

2.  获取数据。

3.  发送数据。

4.  接收和显示数据。

### <a name="next-step"></a>后续步骤

[步骤 1：设置应用程序](step-1-set-up-the-application.md)

