---
title: QueryDef.Updatable Property (DAO)
TOCTitle: Updatable Property
ms:assetid: 9b978b7d-1d76-ff27-a032-dd94660fb088
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198056(v=office.15)
ms:contentKeyID: 48546575
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4ad761c2941cb556ce67c9f716247663220f753f
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25873689"
---
# <a name="querydefupdatable-property-dao"></a>QueryDef.Updatable Property (DAO)


**适用于**： Access 2013、 Office 2013

返回一个值，该值指示是否可以更改 DAO 对象。只读 **Boolean**。

## <a name="syntax"></a>语法

*表达式*。可更新

*表达式*一个代表**QueryDef**对象的变量。

## <a name="remarks"></a>注解

即使生成的 ****Recordset**** 对象不可更新，如果可以更新查询定义，也将 **QueryDef** 对象的 [Updatable](recordset-object-dao.md) 属性设置为 **True**。

