---
title: TableDef.DateCreated 属性 (DAO)
TOCTitle: DateCreated Property
ms:assetid: fedd28e9-41a4-db7f-9ba9-6ada350d594a
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837292(v=office.15)
ms:contentKeyID: 48548947
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: be76ed7f9d358963ea58776327ddafbb66f9d367
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25923138"
---
# <a name="tabledefdatecreated-property-dao"></a>TableDef.DateCreated 属性 (DAO)


**适用于**： Access 2013、 Office 2013

返回对象的创建日期和时间（仅适用于 Microsoft Access 工作区）。只读 **Variant**。

## <a name="syntax"></a>语法

*表达式*。DateCreated

*表达式*一个代表**TableDef**对象的变量。

## <a name="remarks"></a>注解

**DateCreated** 和 **LastUpdated** 返回创建或上次更新对象的日期和时间。在多用户环境中，用户应当直接从文件服务器获取这些设置，以避免在 DateCreated 和 LastUpdated 属性设置中出现差异。

