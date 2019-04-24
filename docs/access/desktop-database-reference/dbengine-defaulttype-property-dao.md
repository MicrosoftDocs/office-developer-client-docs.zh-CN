---
title: DefaultType 属性 (DAO) DBEngine
TOCTitle: DefaultType Property
ms:assetid: b4371f3e-1ce0-1d0f-93a8-0c5329b510ab
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822060(v=office.15)
ms:contentKeyID: 48547217
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053580
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 23f6c87ede6da2cc5b2f3203bfa13cb17bf93e82
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32294377"
---
# <a name="dbenginedefaulttype-property-dao"></a>DefaultType 属性 (DAO) DBEngine


**适用于**：Access 2013、Office 2013

设置或返回一个值，该值指示下一个创建的 **[Workspace](workspace-object-dao.md)** 对象将要使用的工作区类型。

## <a name="syntax"></a>语法

*表达式*。DefaultType

*表达式*一个代表**DBEngine**对象的变量。

## <a name="remarks"></a>注解

该设置值或返回值可以是 **[WorkspaceTypeEnum](workspacetypeenum-enumeration-dao.md)** 常量之一。


> [!NOTE]
> Microsoft Access 2013 中不支持 ODBCDirect 工作区。 如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。

可以通过将 type 参数设置为**[CreateWorkspace](dbengine-createworkspace-method-dao.md)** 方法, 为单个**工作区**重写该设置。

