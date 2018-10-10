---
title: Append 方法 (ADOX Procedures)
TOCTitle: Append Method (ADOX Procedures)
ms:assetid: a93b31bb-e41a-5152-abe7-dd7c2b2fcd0a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249783(v=office.15)
ms:contentKeyID: 48546919
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 5c1afc7aeea90fc152df7d8f7b1601bf3753b3a3
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465880"
---
# <a name="append-method-adox-procedures"></a>Append 方法 (ADOX Procedures)


**适用于**： Access 2013 |Office 2013


将新的 [Procedure](procedure-object-adox.md) 对象添加到 [Procedures](procedures-collection-adox.md) 集合。

## <a name="syntax"></a>语法

*过程*。追加*名称*，*命令*

## <a name="parameters"></a>参数

  - *Name*

  - **String** 值，指定要创建并追加的过程的名称。

  - *Command*

  - 一个 ADO [Command](command-object-ado.md) 对象，表示要创建并追加的过程。

## <a name="remarks"></a>备注

使用在 **Command** 对象中指定的名称和属性在数据源中创建一个新过程。

如果用户指定的命令文本表示视图而非过程，则其行为取决于所使用的提供程序。如果该提供程序不支持保留命令，则 **Append** 将失败。


> [!NOTE]
> <P>使用 Microsoft Jet OLE DB 提供程序，将允许<STRONG>Procedures</STRONG>集合的<STRONG>Append</STRONG>方法，您可以在<EM>命令</EM>参数中指定<STRONG>视图</STRONG>，而不是<STRONG>过程</STRONG>。 该 <STRONG>View</STRONG> 将添加到数据源，并将添加到 <STRONG>Procedures</STRONG> 集合。 执行 <STRONG>Append</STRONG> 之后，如果刷新 <STRONG>Procedures</STRONG> 和 <STRONG>Views</STRONG> 集合，可以看见该 <STRONG>View</STRONG> 不再位于 <STRONG>Procedures</STRONG> 集合中，而是出现在 <STRONG>Views</STRONG> 集合中。</P>


