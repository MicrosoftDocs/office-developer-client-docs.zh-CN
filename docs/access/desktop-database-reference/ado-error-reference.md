---
title: ADO 错误参考
TOCTitle: ADO error reference
ms:assetid: 21cec161-664a-4c18-4458-8117f4f63845
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248997(v=office.15)
ms:contentKeyID: 48543690
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 6a7f756af1422588d99fcffe1ae1413422131b70
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28717235"
---
# <a name="ado-error-reference"></a>ADO 错误参考

**适用于**： Access 2013、 Office 2013

**ErrorValueEnum** 常量描述 ADO 的错误值。若要获得这些枚举常量（包括值）的完整列表，请参阅 [附录 B：ADO 错误](appendix-b-ado-errors.md)。本部分将分析一些更有意思的错误并说明可能引发这些错误的某些特定情况或解决问题的解决方案。下面列出了 **ErrorValueEnum** 常量和短型正小数。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>编号</p></th>
<th><p>ErrorValueEnum 常量</p></th>
<th><p>说明/可能的原因</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>3000</strong></p></td>
<td><p><strong>adErrProviderFailed</strong></p></td>
<td><p>提供程序未能执行请求的操作。</p></td>
</tr>
<tr class="even">
<td><p><strong>3001</strong></p></td>
<td><p><strong>adErrInvalidArgument</strong></p></td>
<td><p>参数类型不正确，或不在可以接受的范围之内，或与其他参数冲突。此错误通常是由 SQL SELECT 语句中的录入错误导致的。例如，拼错的字段名称或表名称可能会导致此错误。当 SELECT 语句中指定的字段或表在数据存储区中不存在时也会发生此错误。</p></td>
</tr>
<tr class="odd">
<td><p><strong>3002</strong></p></td>
<td><p><strong>adErrOpeningFile</strong></p></td>
<td><p>无法打开文件。指定的文件名拼写错误，或者文件已被移动、重命名或删除。在网络上，驱动器可能临时不可用，或网络流量可能阻止了连接。</p></td>
</tr>
<tr class="even">
<td><p><strong>3003</strong></p></td>
<td><p><strong>adErrReadFile</strong></p></td>
<td><p>无法读取文件。没有正确指定文件名称，文件可能已被移动或删除，或者文件可能已损坏。</p></td>
</tr>
<tr class="odd">
<td><p><strong>3004</strong></p></td>
<td><p><strong>adErrWriteFile</strong></p></td>
<td><p>写入文件失败。您可能在已经关闭文件后试图向其中写入，或者文件可能损坏。如果文件位于网络驱动器上，网络短时间的不稳定可能阻止写入网络驱动器。</p></td>
</tr>
<tr class="even">
<td><p><strong>3021</strong></p></td>
<td><p><strong>adErrNoCurrentRecord</strong></p></td>
<td><p>可以是 <strong>BOF</strong> 或 <strong>EOF</strong> 为 True，或者是当前记录已被删除。请求的操作需要当前记录。通过使用 <strong>Find</strong> 或 <strong>Seek</strong> 将记录指针移动到所需的记录来尝试更新记录。如果找不到所需的记录， <strong>EOF</strong> 将为 True。在 <strong>AddNew</strong> 或 <strong>Delete</strong> 失败后，也可能发生此错误，因为这些方法失败时，不存在当前记录。  </p></td>
</tr>
<tr class="odd">
<td><p><strong>3219</strong></p></td>
<td><p><strong>adErrIllegalOperation</strong></p></td>
<td><p>此上下文中不允许操作。</p></td>
</tr>
<tr class="even">
<td><p><strong>3220</strong></p></td>
<td><p><strong>adErrCantChangeProvider</strong></p></td>
<td><p>所提供的提供程序与正在使用的提供程序不同。</p></td>
</tr>
<tr class="odd">
<td><p><strong>3246</strong></p></td>
<td><p><strong>adErrInTransaction</strong></p></td>
<td><p>在事务处理过程中，不能显式关闭 <strong>Connection</strong> 对象。不能关闭当前参与事务的 <strong>Recordset</strong> 或 <strong>Connection</strong> 对象。请在关闭该对象前调用 <strong>RollbackTrans</strong> 或 <strong>CommitTrans</strong> 。  </p></td>
</tr>
<tr class="even">
<td><p><strong>3251</strong></p></td>
<td><p><strong>adErrFeatureNotAvailable</strong></p></td>
<td><p>对象或提供程序不能执行请求的操作。某些操作依赖于特定的提供程序版本。</p></td>
</tr>
<tr class="odd">
<td><p><strong>3265</strong></p></td>
<td><p><strong>adErrItemNotFound</strong></p></td>
<td><p>在对应于所请求的名称或序号的集合中没有找到项。指定的字段名或表名错误。</p></td>
</tr>
<tr class="even">
<td><p><strong>3367</strong></p></td>
<td><p><strong>adErrObjectInCollection</strong></p></td>
<td><p>对象已在集合中。不能追加。一个对象不能向同一集合添加两次。</p></td>
</tr>
<tr class="odd">
<td><p><strong>3420</strong></p></td>
<td><p><strong>adErrObjectNotSet</strong></p></td>
<td><p>对象不再有效。</p></td>
</tr>
<tr class="even">
<td><p><strong>3421</strong></p></td>
<td><p><strong>adErrDataConversion</strong></p></td>
<td><p>应用程序在当前操作中使用了错误类型的值。例如，您可能为需要数据流的操作提供了一个字符串。</p></td>
</tr>
<tr class="odd">
<td><p><strong>3704</strong></p></td>
<td><p><strong>adErrObjectClosed</strong></p></td>
<td><p>对象关闭时不允许操作。 <strong>Connection</strong> 或 <strong>Recordset</strong> 已关闭。例如，某个其他例程可能已经关闭了全局对象。在尝试操作前，可以通过检查 <strong>State</strong> 属性来防止此错误。  </p></td>
</tr>
<tr class="even">
<td><p><strong>3705</strong></p></td>
<td><p><strong>adErrObjectOpen</strong></p></td>
<td><p>对象打开时不允许操作。不能打开已打开的对象。不能将字段追加到打开的 <strong>Recordset</strong> 。  </p></td>
</tr>
<tr class="odd">
<td><p><strong>3706</strong></p></td>
<td><p><strong>adErrProviderNotFound</strong></p></td>
<td><p>找不到提供程序。可能没有正确安装该提供程序。可能没有正确指定该提供程序的名称，指定的提供程序可能没有安装在执行代码的计算机上，或者安装可能已损坏。</p></td>
</tr>
<tr class="even">
<td><p><strong>3707</strong></p></td>
<td><p><strong>adErrBoundToCommand</strong></p></td>
<td><p>不能更改将 <strong>Command</strong> 对象作为源的 <strong>Recordset</strong> 对象的 <strong>ActiveConnection</strong> 属性。应用程序试图将新的 <strong>Connection</strong> 对象分配给将 <strong>Command</strong> 对象作为源的 <strong>Recordset</strong> 。  </p></td>
</tr>
<tr class="odd">
<td><p><strong>3708</strong></p></td>
<td><p><strong>adErrInvalidParamInfo</strong></p></td>
<td><p>没有正确定义 <strong>Parameter</strong> 对象。提供的信息不一致或不完整。  </p></td>
</tr>
<tr class="even">
<td><p><strong>3709</strong></p></td>
<td><p><strong>adErrInvalidConnection</strong></p></td>
<td><p>该连接无法用于执行此操作。它已关闭或在此上下文中无效。</p></td>
</tr>
<tr class="odd">
<td><p><strong>3710</strong></p></td>
<td><p><strong>adErrNotReentrant</strong></p></td>
<td><p>在处理事件的过程中，无法执行操作。不能在导致事件再次触发的事件处理程序中执行操作。例如，不应该从 <strong>WillMove</strong> 事件处理程序中调用 navigation 方法。  </p></td>
</tr>
<tr class="even">
<td><p><strong>3711</strong></p></td>
<td><p><strong>adErrStillExecuting</strong></p></td>
<td><p>在异步执行时，无法执行操作。</p></td>
</tr>
<tr class="odd">
<td><p><strong>3712</strong></p></td>
<td><p><strong>adErrOperationCancelled</strong></p></td>
<td><p>用户已取消操作。应用程序已调用了 <strong>CancelUpdate</strong> 或 <strong>CancelBatch</strong> 方法，当前操作已被取消。  </p></td>
</tr>
<tr class="even">
<td><p><strong>3713</strong></p></td>
<td><p><strong>adErrStillConnecting</strong></p></td>
<td><p>异步连接时，无法执行操作。</p></td>
</tr>
<tr class="odd">
<td><p><strong>3714</strong></p></td>
<td><p><strong>adErrInvalidTransaction</strong></p></td>
<td><p>协调事务无效或未开始。</p></td>
</tr>
<tr class="even">
<td><p><strong>3715</strong></p></td>
<td><p><strong>adErrNotExecuting</strong></p></td>
<td><p>没有执行时，无法执行操作。</p></td>
</tr>
<tr class="odd">
<td><p><strong>3716</strong></p></td>
<td><p><strong>adErrUnsafeOperation</strong></p></td>
<td><p>此计算机上的安全设置禁止访问其他域上的数据源。</p></td>
</tr>
<tr class="even">
<td><p><strong>3717</strong></p></td>
<td><p><strong>adWrnSecurityDialog</strong></p></td>
<td><p>仅供内部使用。不要使用。（为了完整性而包括此项。此错误不应出现在您的代码中。）</p></td>
</tr>
<tr class="odd">
<td><p><strong>3718</strong></p></td>
<td><p><strong>adWrnSecurityDialogHeader</strong></p></td>
<td><p>仅供内部使用。不要使用。（为了完整性而包括此项。此错误不应出现在您的代码中。）</p></td>
</tr>
<tr class="even">
<td><p><strong>3719</strong></p></td>
<td><p><strong>adErrIntegrityViolation</strong></p></td>
<td><p>数据值与字段的完整性约束冲突。 <strong>Field</strong> 的新值会导致重复键。构成两条记录之间关系的一方的值可能无法更新。  </p></td>
</tr>
<tr class="odd">
<td><p><strong>3720</strong></p></td>
<td><p><strong>adErrPermissionDenied</strong></p></td>
<td><p>权限不足，无法写入字段。在连接字符串中指定的用户没有适当的权限写入 <strong>字段</strong> 。  </p></td>
</tr>
<tr class="even">
<td><p><strong>3721</strong></p></td>
<td><p><strong>adErrDataOverflow</strong></p></td>
<td><p>数据值过大，无法以字段数据类型表示。为要使用的字段指定的数值过大。例如，将长整型值赋值给短整型字段。</p></td>
</tr>
<tr class="odd">
<td><p><strong>3722</strong></p></td>
<td><p><strong>adErrSchemaViolation</strong></p></td>
<td><p>数据值与数据类型或字段的约束冲突。数据存储区具有不同于 <strong>Field</strong> 值的有效性约束。  </p></td>
</tr>
<tr class="even">
<td><p><strong>3723</strong></p></td>
<td><p><strong>adErrSignMismatch</strong></p></td>
<td><p>转换失败，原因是数据值有符号，而提供程序所使用的字段数据类型无符号。</p></td>
</tr>
<tr class="odd">
<td><p><strong>3724</strong></p></td>
<td><p><strong>adErrCantConvertvalue</strong></p></td>
<td><p>由于符号不匹配或数据溢出以外的其他原因，数据值无法转换。例如，转换会截断数据。</p></td>
</tr>
<tr class="even">
<td><p><strong>3725</strong></p></td>
<td><p><strong>adErrCantCreate</strong></p></td>
<td><p>因为字段数据类型未知，或提供程序没有足够的资源执行该操作，无法设置或检索数据值。</p></td>
</tr>
<tr class="odd">
<td><p><strong>3726</strong></p></td>
<td><p><strong>adErrColumnNotOnThisRow</strong></p></td>
<td><p>记录不包含此字段。指定的字段名称不正确，或所引用字段不是当前记录的 <strong>Fields</strong> 集合中的字段。  </p></td>
</tr>
<tr class="even">
<td><p><strong>3727</strong></p></td>
<td><p><strong>adErrURLDoesNotExist</strong></p></td>
<td><p>源 URL 或目标 URL 的父级不存在。 源或目标 URL 中没有发生打字错误。 您可能必须https://mysite/photo/myphoto.jpg时，可能键入了https://mysite/photos/myphoto.jpg相反。 在父 URL （在此情况下，而不是<em>照片</em><em>照片</em>） 发生打字错误已导致错误。</p></td>
</tr>
<tr class="odd">
<td><p><strong>3728</strong></p></td>
<td><p><strong>adErrTreePermissionDenied</strong></p></td>
<td><p>权限不足，无法访问树或子树。连接字符串中指定的用户没有适当的权限。</p></td>
</tr>
<tr class="even">
<td><p><strong>3729</strong></p></td>
<td><p><strong>adErrInvalidURL</strong></p></td>
<td><p>URL 包含无效字符。请确保键入的 URL 正确。URL 遵循注册到当前提供程序的架构（例如，为 http 注册了 Internet Publishing Provider）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>3730</strong></p></td>
<td><p><strong>adErrResourceLocked</strong></p></td>
<td><p>由指定的 URL 表示的对象被一个或多个其他进程锁定。请等待该进程完成，然后重试该操作。试图访问的对象已被其他用户或应用程序中的其他进程锁定。在多用户环境中，很可能出现这种情况。</p></td>
</tr>
<tr class="even">
<td><p><strong>3731</strong></p></td>
<td><p><strong>adErrResourceExists</strong></p></td>
<td><p>无法执行复制操作。由目标 URL 命名的对象已经存在。指定 <strong>adCopyOverwrite</strong> 替换该对象。如果在复制目录中的文件时不指定 <strong>adCopyOverwrite</strong> ，则在试图复制已存在于目标位置的项时，复制会失败。  </p></td>
</tr>
<tr class="odd">
<td><p><strong>3732</strong></p></td>
<td><p><strong>adErrCannotComplete</strong></p></td>
<td><p>服务器无法完成该操作。这可能是由于服务器忙于其他操作，或者服务器资源不足。</p></td>
</tr>
<tr class="even">
<td><p><strong>3733</strong></p></td>
<td><p><strong>adErrVolumeNotFound</strong></p></td>
<td><p>提供程序找不到 URL 指定的存储设备。请确保键入的 URL 正确。存储设备的 URL 可能不正确，但其他原因也可能引起此错误。设备可能处于脱机状态，或者大量的网络流量可能会阻止建立连接。</p></td>
</tr>
<tr class="odd">
<td><p><strong>3734</strong></p></td>
<td><p><strong>adErrOutOfSpace</strong></p></td>
<td><p>无法执行操作。提供程序无法获取足够的存储空间。RAM 或硬盘空间不足，无法满足服务器上临时文件的需求。</p></td>
</tr>
<tr class="even">
<td><p><strong>3735</strong></p></td>
<td><p><strong>adErrResourceOutOfScope</strong></p></td>
<td><p>源 URL 或目标 URL 在当前记录的范围之外。</p></td>
</tr>
<tr class="odd">
<td><p><strong>3736</strong></p></td>
<td><p><strong>adErrUnavailable</strong></p></td>
<td><p>操作未能完成，状态不可用。可能是字段不可用或未尝试任何操作。其他用户可能已经更改或删除了您试图访问的字段。</p></td>
</tr>
<tr class="even">
<td><p><strong>3737</strong></p></td>
<td><p><strong>adErrURLNamedRowDoesNotExist</strong></p></td>
<td><p>此 URL 指定的记录不存在。在试图使用 <strong>Record</strong> 对象打开文件时，文件名或文件路径拼写错误。  </p></td>
</tr>
<tr class="odd">
<td><p><strong>3738</strong></p></td>
<td><p><strong>adErrDelResOutOfScope</strong></p></td>
<td><p>要删除的对象的 URL 位于当前记录的范围之外。</p></td>
</tr>
<tr class="even">
<td><p><strong>3747</strong></p></td>
<td><p><strong>adErrCatalogNotSet</strong></p></td>
<td><p>操作需要一个有效的 <strong>ParentCatalog</strong> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>3748</strong></p></td>
<td><p><strong>adErrCantChangeConnection</strong></p></td>
<td><p>连接被拒绝。所请求的新连接与已使用的连接具有不同的特征。</p></td>
</tr>
<tr class="even">
<td><p><strong>3749</strong></p></td>
<td><p><strong>adErrFieldsUpdateFailed</strong></p></td>
<td><p>字段更新失败。 有关详细信息，请检查单个 field 对象的<strong>Status</strong>属性。 两种情况下会出现此错误： 时更改在更改或添加记录到数据库; 过程中的<strong>Field</strong>对象的值和时更改<strong>Field</strong>对象本身的属性。 由于问题中当前记录的字段的一个失败的<strong>Record</strong>或<strong>Recordset</strong>的更新。 枚举的<strong>字段</strong>集合，并检查每个字段，以确定问题的原因的<strong>状态</strong>属性。</p></td>
</tr>
<tr class="odd">
<td><p><strong>3750</strong></p></td>
<td><p><strong>adErrDenyNotSupported</strong></p></td>
<td><p>提供程序不支持共享限制。试图限制文件共享，但您的提供程序不支持该概念。</p></td>
</tr>
<tr class="even">
<td><p><strong>3751</strong></p></td>
<td><p><strong>adErrDenyTypeNotSupported</strong></p></td>
<td><p>提供程序不支持所请求的共享限制类型。试图建立特殊类型的文件共享限制，您的提供程序不支持该限制。请参阅提供程序的文档以确定所支持的文件共享限制。</p></td>
</tr>
</tbody>
</table>

