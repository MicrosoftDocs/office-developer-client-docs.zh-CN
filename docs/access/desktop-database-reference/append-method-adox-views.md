---
title: Append 方法 (ADOX Views)
TOCTitle: Append Method (ADOX Views)
ms:assetid: 202f1d0a-dc5d-84e5-daf3-3212e5bc6088
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248985(v=office.15)
ms:contentKeyID: 48543655
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 106dd9d72cb350422f00da05859bc096cb2b52e9
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467261"
---
# <a name="append-method-adox-views"></a>Append 方法 (ADOX Views)


**适用于**： Access 2013 |Office 2013


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
> <P>使用 Microsoft Jet OLE DB 提供程序，将允许<STRONG>Views</STRONG>集合的<STRONG>Append</STRONG>方法，您可以在<EM>命令</EM>参数中指定<STRONG>过程</STRONG>而不是<STRONG>视图</STRONG>。 该 <STRONG>Procedure</STRONG> 将添加到数据源，并将添加到 <STRONG>Views</STRONG> 集合。 执行 <STRONG>Append</STRONG> 之后，如果刷新 <STRONG>Procedures</STRONG> 和 <STRONG>Views</STRONG> 集合，可以看到该 <STRONG>Procedure</STRONG> 不再位于 <STRONG>Views</STRONG> 集合中，而是出现在 <STRONG>Procedures</STRONG> 集合中。</P>


