---
title: DBEngine.Version 属性 (DAO)
TOCTitle: Version Property
ms:assetid: b2807dc1-604f-4423-289a-ff38a3d9f31b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822024(v=office.15)
ms:contentKeyID: 48547171
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052986
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 1723deea7f29c59fb388a11acc5e5ffcced4abe1
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25924594"
---
# <a name="dbengineversion-property-dao"></a>DBEngine.Version 属性 (DAO)


**适用于**： Access 2013、 Office 2013

返回当前使用的 DAO 版本。只读 **String**。

## <a name="syntax"></a>语法

*表达式*。版本

*表达式*一个代表**DBEngine**对象的变量。

## <a name="remarks"></a>说明

该返回值为 String 类型，其计算结果为“major.minor”格式的版本号。例如，“3.0”。产品版本号由版本号 (3)、句点和发行版本号 (0) 组成。

