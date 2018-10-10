---
title: 持久化分层记录集
TOCTitle: Persisting Hierarchical Recordsets
ms:assetid: 28f48d4a-1c32-7b60-cd65-51fb87c5380e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249048(v=office.15)
ms:contentKeyID: 48543872
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 36c6c1d99b01918d848dfde06c26ad6851b1db43
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467329"
---
# <a name="persisting-hierarchical-recordsets"></a>持久化分层记录集


**适用于**： Access 2013 |Office 2013

通过调用 [Save](save-method-ado.md) 方法，可以将分层 **Recordset** 以 ADTG 或 XML 格式保存在文件中。不过，在以 XML 格式保存分层 **Recordset** 时，存在两个限制条件：一是如果分层 **Recordset** 中包含未决更新，则不能保存为 XML 格式；二是不能保存参数化分层 **Recordset**。

有关数据定形提供程序的详细信息，请参阅 [Microsoft Data Shaping Service for OLE DB](microsoft-data-shaping-service-for-ole-db-ado-service-provider.md) (ADO) 和"Data Shaping Service for OLE DB(OLE DB)"。

