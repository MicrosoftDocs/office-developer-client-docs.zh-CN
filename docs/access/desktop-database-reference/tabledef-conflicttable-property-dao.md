---
title: TableDef.ConflictTable Property (DAO)
TOCTitle: ConflictTable Property
ms:assetid: 0db8b975-eb6d-19c6-cfb7-6ce01230ebe4
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845218(v=office.15)
ms:contentKeyID: 48543228
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053356
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 81b7793291575ca86b5eec628ac9472a20d90ce4
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25870658"
---
# <a name="tabledefconflicttable-property-dao"></a>TableDef.ConflictTable Property (DAO)


**适用于**： Access 2013、 Office 2013

返回冲突表（其中包含同步两个副本的过程中发生冲突的数据库记录）的名称（仅适用于 Microsoft Access 工作区）。只读 **String**。

## <a name="syntax"></a>语法

*表达式*。ConflictTable

*表达式*一个返回**TableDef**对象的表达式。

## <a name="remarks"></a>注解

如果不存在冲突表，或者数据库不是副本，则返回值为 **String** 数据类型的零长度字符串 ("")。

如果两个用户在不同的副本位置对数据库中的相同记录各自执行了更改，则其中一个用户所做的更改将无法应用到另一个副本。因此，更改失败的那个用户必须解决冲突。

冲突是在记录级别发生的，而不是在字段之间发生的。例如，如果一个用户更改了 Address 字段，而另一个用户更新了同一记录中的 Phone 字段，则会拒绝其中一项更改。由于冲突在记录级别发生，因此，即使成功的更改和拒绝的更改在事实上不太可能会导致信息冲突，也会发生拒绝。

同步机制通过创建冲突表来处理记录冲突。冲突表包含本应在更改成功后放入到表中的信息。您可以检查这些冲突表，并逐行处理，修复一切适用的项目。

所有冲突表已都命名表\_冲突，其中 table 是表中，截断为最大的表名称长度的原始名称。

