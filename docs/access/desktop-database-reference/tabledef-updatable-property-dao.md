---
title: TableDef.Updatable 属性 (DAO)
TOCTitle: Updatable Property
ms:assetid: 0b1ae7e5-416d-06f0-5d74-989c6db67ff2
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845128(v=office.15)
ms:contentKeyID: 48543168
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 71202203588182ba2bf1ba1449f2b1ee04c82c67
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25926197"
---
# <a name="tabledefupdatable-property-dao"></a>TableDef.Updatable 属性 (DAO)


**适用于**： Access 2013、 Office 2013

返回一个值，该值指示是否可以更改 DAO 对象。只读 **Boolean**。

## <a name="syntax"></a>语法

*表达式*。可更新

*表达式*一个代表**TableDef**对象的变量。

## <a name="remarks"></a>注解

对于新创建的 **TableDef** 对象， **Updatable** 属性设置始终为 **True**；对于链接的 **TableDef** 对象，该属性始终为 **False**。新 **TableDef** 对象只能追加到当前用户拥有写权限的数据库中。

