---
title: Parameter.Value Property (DAO)
TOCTitle: Value Property
ms:assetid: 7058f3cd-9102-c711-bc83-b1565a8b001c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195733(v=office.15)
ms:contentKeyID: 48545556
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 21aef110b73b851c83af95fbc7cbf1de47d10747
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25870007"
---
# <a name="parametervalue-property-dao"></a>Parameter.Value Property (DAO)


**适用于**： Access 2013、 Office 2013

设置或返回对象的值。可读/写 **Variant** 类型。

## <a name="syntax"></a>语法

*表达式*。值

*表达式*一个代表**Parameter**对象的变量。

## <a name="remarks"></a>注解

设置或返回值是 Variant 数据类型，其计算结果值属于对象的 **Type** 属性所指定的数据类型。

通常， **Value** 属性用于检索和更改 **Recordset** 对象中的数据。

**Value** 属性是 **Field**、 **Parameter** 和 **Property** 对象的默认属性。因此，您可以通过直接引用这些对象（而不是指定 **Value** 属性）来设置或返回这些对象之一的值。

如果尝试在不正确的上下文中设置或返回 **Value** 属性（例如 **TableDef** 对象的 **Fields** 集合中 **Field** 对象的 **Value** 属性），则会导致可捕获的错误。


> [!NOTE]
> <P>从 Microsoft SQL Server 数据库读取小数值时，在 Microsoft Access 工作区中将使用科学计数法设置这些值的格式，但是这些值在 ODBCDirect 工作区中仍显示为普通的小数值。</P>


