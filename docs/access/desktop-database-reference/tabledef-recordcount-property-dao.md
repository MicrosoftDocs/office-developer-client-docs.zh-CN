---
title: TableDef.RecordCount 属性 (DAO)
TOCTitle: RecordCount Property
ms:assetid: f8804244-0134-fc1f-1f5f-4971afe17974
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836946(v=office.15)
ms:contentKeyID: 48548783
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4b24aaa5aec9b17adc169c67733a19a9077a4930
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25920919"
---
# <a name="tabledefrecordcount-property-dao"></a>TableDef.RecordCount 属性 (DAO)


**适用于**： Access 2013、 Office 2013

返回 **[TableDef](tabledef-object-dao.md)** 对象中的总记录数。 **Long** 类型，只读。

## <a name="syntax"></a>语法

*表达式*。RecordCount

*表达式*一个代表**TableDef**对象的变量。

## <a name="remarks"></a>注解

如果 **Recordset** 或 **TableDef** 对象不含记录，则其 **RecordCount** 属性设置为 0。

当使用链接的 **TableDef** 对象时，**RecordCount** 属性设置始终为 -1。

