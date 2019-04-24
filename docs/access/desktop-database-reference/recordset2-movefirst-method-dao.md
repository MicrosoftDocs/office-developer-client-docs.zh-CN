---
title: MoveFirst 方法 (DAO) Recordset2
TOCTitle: MoveFirst Method
ms:assetid: 74b186d0-8f6a-d136-a563-04f58d67b122
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195879(v=office.15)
ms:contentKeyID: 48545667
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: a54658e1259a49a1c92facf988076e6b6e1dd961
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309658"
---
# <a name="recordset2movefirst-method-dao"></a>MoveFirst 方法 (DAO) Recordset2


**适用于**：Access 2013、Office 2013

移到指定的 **Recordset** 对象中的第一条记录，并使该记录成为当前记录。

## <a name="syntax"></a>语法

*表达式*。MoveFirst

*表达式*一个代表**Recordset2**对象的变量。

## <a name="remarks"></a>注解

使用 **Move** 方法可以在记录间移动，而不需要应用条件。

如果要编辑当前记录，请确保使用 **Update** 方法保存更改，然后移到另一条记录。如果在不更新的情况下移到另一条记录，则更改将会丢失，且不发出警告。

在打开 **Recordset** 时，第一条记录将是当前记录，并且 **BOF** 属性为 **False**。如果 **Recordset** 不包含记录，则 **BOF** 属性为 **True**，并且不存在当前记录。

如果在使用 **MoveFirst** 或 **MoveLast** 时，第一条或最后一条记录已经是当前记录，则当前记录不会更改。

如果 recordset 引用表类型的**recordset** (仅适用于 Microsoft Access 工作区), 则移动将遵循当前索引。 可以使用 **Index** 属性设置当前索引。 如果不设置当前索引，则返回记录的顺序将是不确定的。

您不能在仅向前类型的**Recordset**对象上使用**MoveFirst**、 **MoveLast**和**MovePrevious**方法。

若要将 **Recordset** 对象中的当前记录的位置向前或向后移动指定的记录数，请使用 **Move** 方法。

