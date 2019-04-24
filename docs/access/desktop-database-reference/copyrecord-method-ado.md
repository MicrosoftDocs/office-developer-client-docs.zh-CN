---
title: CopyRecord 方法 (ADO)
TOCTitle: CopyRecord method (ADO)
ms:assetid: 724e4358-f216-8e47-5bab-c72770ece5a4
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249459(v=office.15)
ms:contentKeyID: 48545605
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c5aac745bacf0662f6cd389bfefde7182a9676d3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295525"
---
# <a name="copyrecord-method-ado"></a>CopyRecord 方法 (ADO)

**适用于**：Access 2013、Office 2013

用于将由 **Record** 表示的实体复制到其他位置。

## <a name="syntax"></a>语法

*记录*。CopyRecord (*源*、*目标*、*用户名*、*密码*、*选项*、*异步*)

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*Source* |可选。**字符串型**值，包含用于指定要复制的实体（如文件或目录）的 URL。如果忽略 *Source* 或者指定一个空字符串，将复制由当前 [Record](record-object-ado.md) 表示的文件或目录。|
|*目标* |可选。 **字符串型**值，包含用于指定 *Source* 将复制到的位置的 URL。|
|*UserName* |可选。 包含用户 ID 的**字符串型**值，如果需要，将授予访问 *Destination* 的权限。|
|*Password* |可选。 包含密码的**字符串型**值，如果需要，将验证 *UserName*。|
|*Options* |可选。[CopyRecordOptionsEnum](copyrecordoptionsenum.md) 值，其默认值为 **adCopyUnspecified** 。指定该方法的行为。|
|*Async* |可选。一个 **Boolean** 值，为 **True** 时，指定此操作应为异步。|

## <a name="return-value"></a>返回值

**字符串型**值，通常返回 *Destination* 的值。 不过，返回的确切值与提供程序有关。

## <a name="remarks"></a>注解

*Source* 和 *Destination* 的值不能相同；否则，将发生运行时错误。服务器、路径和资源名中必须至少有一个不同。

除非指定 **adCopyNonRecursive**，否则 *Source* 的所有子级（如子目录）以递归方式进行复制。在递归操作中，*Destination* 不能是 *Source* 的子目录；否则，操作将无法完成。

如果 *Destination* 标识现有的实体（如文件或目录），该方法将失败，除非指定了 **adCopyOverWrite**。

> [!IMPORTANT]
> 应谨慎使用 **adCopyOverWrite** 选项。例如，在将文件复制到目录时指定此选项将*删除*该目录并替换为复制的文件。


> [!NOTE]
> [!注释] 使用 HTTP 架构的 URL 将自动调用 [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)。 有关详细信息, 请参阅[绝对和相对 url](absolute-and-relative-urls.md)。


