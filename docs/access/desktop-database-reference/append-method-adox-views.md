---
title: Append 方法（ADOX 视图）
TOCTitle: Append method (ADOX Views)
ms:assetid: 202f1d0a-dc5d-84e5-daf3-3212e5bc6088
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248985(v=office.15)
ms:contentKeyID: 48543655
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ccba425e74321f4ab760e9ddc4a722295290ffd1
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25925154"
---
# <a name="append-method-adox-views"></a>Append 方法（ADOX 视图）


**适用于**： Access 2013、 Office 2013


创建一个新的 [View](view-object-adox.md) 对象，并将其追加到 [Views](views-collection-adox.md) 集合。

## <a name="syntax"></a>语法

*视图*。追加*名称*，*命令*

## <a name="parameters"></a>参数

  - *Name*

  - **String** 值，指定要创建的视图的名称。

  - *Command*

  - 一个表示要创建的视图的 ADO [Command](command-object-ado.md) 对象。

## <a name="remarks"></a>备注

使用在 **Command** 对象中指定的名称和属性在数据源中创建一个新视图。

如果用户指定的命令文本表示过程而非视图，则其行为取决于提供程序。如果该提供程序不支持保留命令，则 **Append** 将失败。


> [!NOTE]
> 使用 Microsoft Jet OLE DB 提供程序，将允许**Views**集合的**Append**方法，您可以在*命令*参数中指定**过程**而不是**视图**。 该 **Procedure** 将添加到数据源，并将添加到 **Views** 集合。 执行 **Append** 之后，如果刷新 **Procedures** 和 **Views** 集合，可以看到该 **Procedure** 不再位于 **Views** 集合中，而是出现在 **Procedures** 集合中。


