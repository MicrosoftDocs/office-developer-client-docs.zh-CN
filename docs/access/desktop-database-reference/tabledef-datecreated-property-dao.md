---
title: TableDef.DateCreated Property (DAO)
TOCTitle: DateCreated Property
ms:assetid: fedd28e9-41a4-db7f-9ba9-6ada350d594a
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837292(v=office.15)
ms:contentKeyID: 48548947
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6ffad5b1bee5756c969f03a920f453f1d3abf9e3
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466189"
---
# <a name="tabledefdatecreated-property-dao"></a>TableDef.DateCreated Property (DAO)


**适用于**： Access 2013 |Office 2013

返回对象的创建日期和时间（仅适用于 Microsoft Access 工作区）。只读 **Variant**。

## <a name="syntax"></a>语法

*表达式*。DateCreated

*表达式*一个代表**TableDef**对象的变量。

## <a name="remarks"></a>注解

**DateCreated** 和 **LastUpdated** 返回创建或上次更新对象的日期和时间。在多用户环境中，用户应当直接从文件服务器获取这些设置，以避免在 DateCreated 和 LastUpdated 属性设置中出现差异。

