---
title: LastUpdated 属性 (DAO)
TOCTitle: LastUpdated Property
ms:assetid: 3b7818d4-054e-54e2-bf63-58b340bb4a90
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192665(v=office.15)
ms:contentKeyID: 48544287
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 1876e92381828075edca3bbfcbae63e706a21365
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303309"
---
# <a name="querydeflastupdated-property-dao"></a>LastUpdated 属性 (DAO)


**适用于**：Access 2013、Office 2013

返回对象的最近更改日期和时间。 只读 **Variant** 类型。

## <a name="syntax"></a>语法

*表达式*。LastUpdated

*表达式*一个代表**QueryDef**对象的变量。

## <a name="remarks"></a>注解

**DateCreated** 和 **LastUpdated** 返回创建或上次更新对象的日期和时间。在多用户环境中，用户应当直接从文件服务器获取这些设置，以避免在 DateCreated 和 LastUpdated 属性设置中出现差异。

