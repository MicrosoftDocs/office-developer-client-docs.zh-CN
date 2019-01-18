---
title: 使用页面 （访问桌面数据库参考 （英文）
TOCTitle: Using Pages
ms:assetid: 516fb7c2-c7a2-385b-83e7-2091c7283ea2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249261(v=office.15)
ms:contentKeyID: 48544817
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 92d6185c3234a58ea9a84310291d0c37e0272535
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28709402"
---
# <a name="using-pages"></a>使用页面


**适用于**： Access 2013、 Office 2013

使用 **PageCount** 属性可以确定 **Recordset** 对象中的数据页数。 *页面*是其大小等于**PageSize**属性设置的记录组。 即使最后一页由于记录数小于 **PageSize** 值而不完整，它也被视作 **PageCount** 值中的另一页。 如果 **Recordset** 对象不支持此属性， **PageCount** 将为 -1，这指示 **PageCount** 是不可确定的。

使用 **PageSize** 属性可以确定逻辑数据页由多少记录组成。建立页大小允许您使用 **AbsolutePage** 属性来移到特定页的第一个记录。这对于 Web 服务器方案非常有用，此时您希望允许用户逐页浏览数据，并一次查看特定数量的记录。

可随时设置此属性，并将其值用于计算特定页的首条记录的位置。

使用 **AbsolutePage** 属性可以确定当前记录所在页的页码。另外，提供程序必须支持相应的功能，才能使该属性可用。

**AbsolutePage** 从 1 开始，如果当前的记录是 **Recordset** 中的第一个记录时，此属性将等于 1。设置此属性可以移到特定页的第一个记录。可以从 **PageCount** 属性获取总页数。

