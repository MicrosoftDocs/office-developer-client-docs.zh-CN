---
title: CopyRecord 方法 (ADO)
TOCTitle: CopyRecord method (ADO)
ms:assetid: 724e4358-f216-8e47-5bab-c72770ece5a4
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249459(v=office.15)
ms:contentKeyID: 48545605
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 161cfec0e8450ef7e80c47bc8fb1b8304790e7c5
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25949906"
---
# <a name="copyrecord-method-ado"></a>CopyRecord 方法 (ADO)

**适用于**： Access 2013、 Office 2013

用于将由 **Record** 表示的实体复制到其他位置。

## <a name="syntax"></a>语法

*记录*。CopyRecord （*源*、 *Destination*、*用户名*、*密码*、*选项*、*异步*）

## <a name="parameters"></a>参数

|参数|说明|
|:--------|:----------|
|*Source* |可选。 **字符串型** 值，包含用于指定要复制的实体（如文件或目录）的 URL。 如果*源*被省略，或指定为空字符串，将复制的文件或当前[Record](record-object-ado.md)所表示的目录。|
|*Destination* |可选。 一个**字符串**值，包含指定将在其中复制*源*的位置的 URL。|
|*UserName* |可选。包含用户 ID 的**字符串型**值，如果需要，将授予访问 *Destination* 的权限。|
|*Password* |可选。包含密码的**字符串型**值，如果需要，将验证 *UserName*。|
|*Options* |可选。[CopyRecordOptionsEnum](copyrecordoptionsenum.md) 值，其默认值为 **adCopyUnspecified** 。指定该方法的行为。|
|*Async* |可选。一个 **Boolean** 值，为 **True** 时，指定此操作应为异步。|

## <a name="return-value"></a>返回值

**字符串型**值，通常返回 *Destination* 的值。不过，返回的确切值与提供程序有关。

## <a name="remarks"></a>说明

*源*和*目标*值不能相同;否则，将发生运行时错误。 服务器、路径和资源名中必须至少有一个不同。

除非指定 **adCopyNonRecursive**，否则 *Source* 的所有子级（如子目录）以递归方式进行复制。在递归操作中，*Destination* 不能是 *Source* 的子目录；否则，操作将无法完成。

如果*Destination*标识现有实体 （如文件或目录），除非指定了**adCopyOverWrite** ，此方法将失败。

> [!IMPORTANT]
> [!重要信息] 应谨慎使用 **adCopyOverWrite** 选项。 例如，将文件复制到目录时指定此选项将*删除*目录和替换该文件。


> [!NOTE]
> [!注释] 使用 HTTP 架构的 URL 将自动调用 [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)。 有关详细信息，请参阅[绝对和相对 Url](absolute-and-relative-urls.md)。


