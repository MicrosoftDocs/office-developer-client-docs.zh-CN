---
title: Append 方法（ADOX 过程）
TOCTitle: Append method (ADOX Procedures)
ms:assetid: a93b31bb-e41a-5152-abe7-dd7c2b2fcd0a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249783(v=office.15)
ms:contentKeyID: 48546919
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: a2de9dc7d8dccfc4107dbd802c4013ac794acf61
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32297079"
---
# <a name="append-method-adox-procedures"></a>Append 方法（ADOX 过程）

**适用于**：Access 2013、Office 2013

将新的 [Procedure](procedure-object-adox.md) 对象添加到 [Procedures](procedures-collection-adox.md) 集合。

## <a name="syntax"></a>语法

*过程*。追加*名称*、*命令*

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*Name* |**String** 值，指定要创建并追加的过程的名称。|
|*Command* |一个 ADO [Command](command-object-ado.md) 对象，表示要创建并追加的过程。|

## <a name="remarks"></a>注解

使用在 **Command** 对象中指定的名称和属性在数据源中创建一个新过程。

如果用户指定的命令文本表示视图而非过程，则其行为取决于所使用的提供程序。如果该提供程序不支持保留命令，则 **Append** 将失败。

> [!NOTE]
> 使用 OLE DB Provider for Microsoft Jet 时，**Procedures** 集合的 **Append** 方法将使您可以在 **Command** 参数中指定 **View** 而不是 *Procedure*。该 **View** 将添加到数据源，并将添加到 **Procedures** 集合。执行 **Append** 之后，如果刷新 **Procedures** 和 **Views** 集合，可以看见该 **View** 不再位于 **Procedures** 集合中，而是出现在 **Views** 集合中。


