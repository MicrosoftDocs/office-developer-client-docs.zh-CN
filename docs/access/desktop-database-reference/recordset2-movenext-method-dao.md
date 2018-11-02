---
title: Recordset2.MoveNext 方法 (DAO)
TOCTitle: MoveNext Method
ms:assetid: 0eeb917e-f76a-03ec-9e1e-aa8d501db031
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845265(v=office.15)
ms:contentKeyID: 48543254
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e89a82a1449fd1a16e5273531a542332542ecdcd
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25923712"
---
# <a name="recordset2movenext-method-dao"></a>Recordset2.MoveNext 方法 (DAO)


**适用于**： Access 2013、 Office 2013

移到指定的 **Recordset** 对象中的下一条记录，并使该记录成为当前记录。

## <a name="syntax"></a>语法

*表达式*。MoveNext

*表达式*一个表示**Recordset2**对象的变量。

## <a name="remarks"></a>注解

使用 **Move** 方法可以在记录间移动，而不需要应用条件。

如果要编辑当前记录，请确保使用 **Update** 方法保存更改，然后移到另一条记录。如果在不更新的情况下移到另一条记录，则更改将会丢失，且不发出警告。

在打开 **Recordset** 时，第一条记录将是当前记录，并且 **BOF** 属性为 **False**。如果 **Recordset** 不包含记录，则 **BOF** 属性为 **True**，并且不存在当前记录。

如果最后一条记录是当前记录，在使用 **MoveNext** 时， **EOF** 属性将是 **True**，并且不会有当前记录。如果再次使用 **MoveNext**，将发生错误，同时 **EOF** 保留为 **True**。

如果 recordset 引用表类型**Recordset** （仅限 Microsoft Access 工作区），则移动遵循当前索引。 可以使用 **Index** 属性设置当前索引。 如果不设置当前索引，则返回记录的顺序将是不确定的。

不能对仅向前类型**Recordset**对象使用**MoveFirst**、 **MoveLast**和**MovePrevious**方法。

若要将 **Recordset** 对象中的当前记录的位置向前或向后移动指定的记录数，请使用 **Move** 方法。

