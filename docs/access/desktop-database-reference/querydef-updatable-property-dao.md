---
title: QueryDef 可更新属性 (DAO)
TOCTitle: Updatable Property
ms:assetid: 9b978b7d-1d76-ff27-a032-dd94660fb088
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198056(v=office.15)
ms:contentKeyID: 48546575
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c5321e834f1dd5ed663033cacb530962d7beeb5a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303330"
---
# <a name="querydefupdatable-property-dao"></a>QueryDef 可更新属性 (DAO)


**适用于**：Access 2013、Office 2013

返回一个值，该值指示是否可以更改 DAO 对象。 只读 **Boolean** 类型。

## <a name="syntax"></a>语法

*表达式*。更新

*表达式*一个代表**QueryDef**对象的变量。

## <a name="remarks"></a>注解

即使生成的 **[Recordset](recordset-object-dao.md)** 对象不可更新，如果可以更新查询定义，也将 **QueryDef** 对象的 **Updatable** 属性设置为 **True**。

