---
title: Open 方法（ADO 流）
TOCTitle: Open method (ADO Stream)
ms:assetid: fa2e6aaa-e9f5-009c-f3a0-050a00abf9b0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250275(v=office.15)
ms:contentKeyID: 48548833
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 3a943209ce329d59fb4846ed18fd008bc45803da
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288383"
---
# <a name="open-method-ado-stream"></a>Open 方法（ADO 流）


**适用于**：Access 2013、Office 2013


用于打开 [Stream](stream-object-ado.md) 对象，以操作二进制数据流或文本数据流。

## <a name="syntax"></a>语法

*Stream*。 开放*源代码*、*模式*、 *OpenOptions*、*用户名*、*密码*

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*Source* |可选。 **变量型** 值，用于指定 **Stream** 的数据源。 *Source*可以包含指向已知树结构 (如电子邮件或文件系统) 中的现有节点的绝对 URL 字符串。 应使用 url 关键字 ("url =*方案*:///*服务器*/*文件夹*") 指定 url。 *Source* 也可以包含对已打开的 [Record](record-object-ado.md) 对象的引用，该引用打开与 **Record** 关联的默认流。 如果未指定 *Source*，那么将实例化并打开 **Stream**，且该流默认情况下不与任何基础源关联。 有关 URL 方案及其关联提供程序的详细信息, 请参阅[绝对和相对 url](absolute-and-relative-urls.md)。|
|*Mode* |可选。[ConnectModeEnum](connectmodeenum.md) 值，用于指定生成的 **Stream** 的访问模式（如读/写或只读）。默认值为 **adModeUnknown**。有关访问模式的详细信息，请参阅 [Mode](mode-property-ado.md) 属性。如果未指定 *Mode*，则从源对象继承模式。例如，如果以只读模式打开源 **Record**，则默认情况下 **Stream** 也将以只读模式打开。|
|*OpenOptions* |可选。[StreamOpenOptionsEnum](streamopenoptionsenum.md) 值。默认值为 **adOpenStreamUnspecified** 。|
|*UserName* |可选。包含用户标识的 **字符串型** 值，如果需要，将访问 **Stream** 对象。|
|*Password* |可选。包含密码的 **字符串型** 值，如果需要，将访问 **Stream** 对象。|

## <a name="remarks"></a>注解

将 **Record** 对象作为源参数传入时，不使用 *UserID* 和 *Password* 参数，因为已具有对 **Record** 对象的访问权限。同样，**Record** 对象的 [Mode 属性 (ADO)](mode-property-ado.md) 传送到 **Stream** 对象。如果未指定 *Source*，则打开的 **Stream** 不包含任何数据，且 [Size 属性 (ADO Stream)](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/size-property-ado-stream) 为零 (0)。若要避免在关闭 **Stream** 时丢失写入该 **Stream** 的任何数据，请使用 [CopyTo](copyto-method-ado.md) 或 [SaveToFile](savetofile-method-ado.md) 方法来保存 **Stream**，或者将其保存到其他内存位置。

值为 **adOpenStreamFromRecord** 的 *OpenOptions* 将 *Source* 参数的内容标识为已打开的 **Record** 对象。默认行为是将 *Source* 视为直接指向树结构中的节点（如文件）的 URL。将打开与该节点关联的默认流。

在 **Stream** 未打开时，可以读取 **Stream** 的所有只读属性。如果 **Stream** 是异步打开的，则所有后续操作（检查 [State 属性 (ADO)](state-property-ado.md) 和其他只读属性的操作除外）将被阻止，直到 **Open** 操作完成。

除了上面讨论的选项外，如果不指定 *Source*，可以在内存中只实例化 **Stream** 对象，而不将其与基础源关联。只需使用 [Write](write-method-ado.md) 或 [WriteText](writetext-method-ado.md) 将二进制数据或文本数据写入 **Stream**，或者使用 [LoadFromFile](loadfromfile-method-ado.md) 从文件中加载数据，便可以动态地向流添加数据。

