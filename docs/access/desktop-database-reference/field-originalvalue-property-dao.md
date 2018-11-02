---
title: Field.OriginalValue 属性 (DAO)
TOCTitle: OriginalValue Property
ms:assetid: 69ccec1e-311f-6905-e7bb-ad7fa8277494
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195384(v=office.15)
ms:contentKeyID: 48545418
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d850ebcfef6ea2c08e20ed953dfcc7b5ea23cbab
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25926792"
---
# <a name="fieldoriginalvalue-property-dao"></a>Field.OriginalValue 属性 (DAO)


**适用于**： Access 2013、 Office 2013

## <a name="syntax"></a>语法

*表达式*。OriginalValue

*表达式*一个代表**Field**对象的变量。

## <a name="remarks"></a>注解

在乐观批更新过程中，如果在第一个客户端检索完数据但尚未进行更新尝试时，第二个客户端修改了相同的字段和记录，则会发生冲突。 **OriginalValue** 属性包含上一个批 **Update** 开始时的字段值。如果该值与批 **Update** 尝试写入数据库时数据库中的实际值不匹配，则会发生冲突。如果发生这种情况，可通过 **[VisibleValue](field-visiblevalue-property-dao.md)** 属性访问数据库中的新值。

