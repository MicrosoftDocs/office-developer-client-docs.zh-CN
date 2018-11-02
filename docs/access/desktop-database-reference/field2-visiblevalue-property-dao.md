---
title: Field2.VisibleValue 属性 (DAO)
TOCTitle: VisibleValue Property
ms:assetid: 1e023a1a-fd49-7570-42bd-2f4c06ac5e5e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845809(v=office.15)
ms:contentKeyID: 48543611
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1101184
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 9b33fe61eaeb7d1a6006ffaf4566b65be9f68243
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25926064"
---
# <a name="field2visiblevalue-property-dao"></a>Field2.VisibleValue 属性 (DAO)


**适用于**： Access 2013、 Office 2013

## <a name="syntax"></a>语法

*表达式*。VisibleValue

*表达式*一个代表**Field2**对象的变量。

## <a name="remarks"></a>注解

该属性包含的字段值当前位于服务器上的数据库中。在乐观批更新过程中，如果在第一个客户端检索完数据但尚未进行更新尝试时，第二个客户端修改了相同的字段和记录，则会发生冲突。如果发生这种情况，则可以通过该属性访问第二个客户端设置的值。

