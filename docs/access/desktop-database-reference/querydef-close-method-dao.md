---
title: QueryDef 方法 (DAO)
TOCTitle: Close Method
ms:assetid: b2b63462-453d-9e2b-0bb3-69a4a7a6ecef
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822031(v=office.15)
ms:contentKeyID: 48547179
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052976
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 4d50fa52ff4f5d669b062a052bf3e59a28a9e732
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303302"
---
# <a name="querydefclose-method-dao"></a>QueryDef 方法 (DAO)


**适用于**：Access 2013、Office 2013

关闭已打开的 **QueryDef**。

## <a name="syntax"></a>语法

*表达式*。关闭

*表达式*一个代表**QueryDef**对象的变量。

## <a name="remarks"></a>注解

如果在使用 **Close** 时 **QueryDef** 对象已关闭，将发生运行时错误。

**Close**方法的替代方法是将对象变量的值设置为**nothing** (set dbsTemp = Nothing)。

