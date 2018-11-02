---
title: QueryDef.DateCreated 属性 (DAO)
TOCTitle: DateCreated Property
ms:assetid: f7585b34-8314-fb9f-daa6-cd1a8ad59d91
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836910(v=office.15)
ms:contentKeyID: 48548763
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3eb3d4664f6fce30812904612f458d24f3a8b159
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25927023"
---
# <a name="querydefdatecreated-property-dao"></a>QueryDef.DateCreated 属性 (DAO)


**适用于**： Access 2013、 Office 2013

返回对象的创建日期和时间（仅适用于 Microsoft Access 工作区）。只读 **Variant**。

## <a name="syntax"></a>语法

*表达式*。DateCreated

*表达式*一个代表**QueryDef**对象的变量。

## <a name="remarks"></a>注解

**DateCreated** 和 **LastUpdated** 返回创建或上次更新对象的日期和时间。在多用户环境中，用户应当直接从文件服务器获取这些设置，以避免在 DateCreated 和 LastUpdated 属性设置中出现差异。

