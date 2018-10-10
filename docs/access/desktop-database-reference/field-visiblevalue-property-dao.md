---
title: Field.VisibleValue Property (DAO)
TOCTitle: VisibleValue Property
ms:assetid: e40fcb43-9a1d-69e7-1544-8f15ef21daf4
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835776(v=office.15)
ms:contentKeyID: 48548332
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 892c7b41a692f353ee7e5bdd2191f6e21b8b4cf2
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466285"
---
# <a name="fieldvisiblevalue-property-dao"></a>Field.VisibleValue Property (DAO)


**适用于**： Access 2013 |Office 2013

## <a name="syntax"></a>语法

*表达式*。VisibleValue

*表达式*一个代表**Field**对象的变量。

## <a name="remarks"></a>注解

该属性包含的字段值当前位于服务器上的数据库中。在乐观批更新过程中，如果在第一个客户端检索完数据但尚未进行更新尝试时，第二个客户端修改了相同的字段和记录，则会发生冲突。如果发生这种情况，则可以通过该属性访问第二个客户端设置的值。

