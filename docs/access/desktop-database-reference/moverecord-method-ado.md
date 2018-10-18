---
title: MoveRecord 方法 (ADO)
TOCTitle: MoveRecord Method (ADO)
ms:assetid: efc341a2-0e08-a838-5925-8d4c46377e48
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250217(v=office.15)
ms:contentKeyID: 48548588
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d6955bca1bf693386d1f5edb4bac04cee311d78e
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25606960"
---
# <a name="moverecord-method-ado"></a>MoveRecord 方法 (ADO)


**适用于**： Access 2013 |Office 2013
 

用于将由 [Record](record-object-ado.md) 表示的实体移动到其他位置。

## <a name="syntax"></a>语法

*记录*。MoveRecord （*源*、 *Destination*、*用户名*、*密码*、*选项*、*异步*）

## <a name="parameters"></a>参数

  - *Source*

  - 可选。**字符串型**值，包含标识要移动的 **Record** 的 URL。如果忽略 *Source* 或者指定一个空字符串，将删除由该 **Record** 表示的对象。例如，如果 **Record** 代表文件，则将文件的内容移动到由 *Destination* 指定的位置。

  - *Destination*

  - 可选。 一个**字符串**值，包含指定将移*源*到的位置的 URL。

  - *UserName*

  - 可选。包含用户 ID 的**字符串型**值，如果需要，将授予访问 *Destination* 的权限。

  - *Password*

  - 可选。包含密码的**字符串型**值，如果需要，将通过该密码验证 *UserName*。

  - *Options*

  - 可选。[MoveRecordOptionsEnum](moverecordoptionsenum.md) 值，其默认值为 **adMoveUnspecified** 。指定该方法的行为。

  - *Async*

  - 可选。 **Boolean** 值，为 **True** 时，指定此操作应为异步。

<<<<<<< 标头
## <a name="return-value"></a>返回值
=======
## <a name="return-value"></a>返回值
>>>>>>> master

**字符串型** 值。 通常情况下，则返回的*目标*值。 但是，返回的确切值与提供程序有关。

## <a name="remarks"></a>说明

*源*和*目标*值不能相同;否则，将发生运行时错误。 至少服务器、路径和资源名必须不同。

对于使用 Internet Publishing Provider 移动的文件，该方法更新被移动文件中的所有超文本链接，除非 *Options* 另有指定。如果 *Destination* 标识现有的对象（如文件或目录），该方法将失败，除非指定 **adMoveOverWrite**。


> [!NOTE]
> <P>[!注释] 应谨慎使用 <STRONG>adMoveOverWrite</STRONG> 选项。例如，在将文件移动到目录时指定此选项将删除该目录并替换为复制的文件。</P>



**Record** 对象的某些属性（如 [ParentURL](parenturl-property-ado.md) 属性）在该操作完成后不会更新。可以通过以下方法来刷新 **Record** 对象的属性：关闭 **Record** ，然后使用文件或目录移动到的位置的 URL 重新打开该记录。

如果此 **Record** 是从 [Recordset](recordset-object-ado.md) 获取的，则移动的文件或目录的新位置将不会立即反映到 **Recordset** 中。您可以刷新 **Recordset** ，方法是关闭并重新打开它。


> [!NOTE]
<<<<<<< 标头
> <P>[!注释] 使用 HTTP 架构的 URL 将自动调用 <A href="microsoft-ole-db-provider-for-internet-publishing.md">Microsoft OLE DB Provider for Internet Publishing</A>。有关详细信息，请参阅<A href="absolute-and-relative-urls.md">绝对 URL 和相对 URL</A>。</P>
=======
> [!注释] 使用 HTTP 架构的 URL 将自动调用 [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)。 有关详细信息，请参阅[绝对和相对 Url](absolute-and-relative-urls.md)。
>>>>>>> master


