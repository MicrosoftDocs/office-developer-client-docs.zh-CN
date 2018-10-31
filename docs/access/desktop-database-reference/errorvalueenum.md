---
title: ErrorValueEnum （访问桌面数据库参考 （英文）
TOCTitle: ErrorValueEnum
ms:assetid: 2af99f32-6004-1225-367c-45d693f447b8
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249058(v=office.15)
ms:contentKeyID: 48543921
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: 5e9da9b9c197bb9917d2184e07a76bdfb25bd031
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25860859"
---
# <a name="errorvalueenum"></a>ErrorValueEnum

**适用于**： Access 2013 |Office 2013

指定 ADO 运行时错误的类型。

下面列出了三种格式的错误号：

- 正十进制 - 十进制格式的完整编号的两个低位字节。此编号显示在默认的 Visual Basic 错误消息对话框中。例如，运行时错误"3707"。

- 负十进制 - 完整错误号的十进制转换形式。

- 十六进制 - 完整错误号的十六进制表示。Windows 设备代码在第四位。ADO 错误号的设备代码为 *A*。例如：0x800***A***0E7B。

> [!NOTE]
> OLE DB 错误可能被传递给 ADO 应用程序。 通常，这些可以由*4*个 Windows 设施代码标识。 例如，0x800_**4**_...有关这些号码的详细信息，请参阅第 16 章*OLE DB 程序员参考 （英文）。*

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>常量</p></th>
<th><p>值</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>adErrBoundToCommand</strong></p></td>
<td><p>3707<br />
-2146824581<br />
0x800A0E7B</p></td>
<td><p>无法更改以 <strong>Command</strong> 对象为源的 <strong>Recordset</strong> 对象的 <strong>ActiveConnection</strong> 属性。</p></td>
</tr>
<tr class="even">
<td><p><strong>adErrCannotComplete</strong></p></td>
<td><p>3732<br />
-2146824556<br />
0x800A0E94</p></td>
<td><p>服务器无法完成操作。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adErrCantChangeConnection</strong></p></td>
<td><p>3748<br />
-2146824540<br />
0x800A0EA4</p></td>
<td><p>连接被拒绝。请求的新连接和已被使用的连接的特性不一致。</p></td>
</tr>
<tr class="even">
<td><p><strong>adErrCantChangeProvider</strong></p></td>
<td><p>3220<br />
-2146825068<br />
0X800A0C94</p></td>
<td><p>所提供的提供程序与正在使用的提供程序不同。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adErrCantConvertvalue</strong></p></td>
<td><p>3724<br />
-2146824564<br />
0x800A0E8C</p></td>
<td><p>由于符号不匹配或数据溢出以外的其他原因，数据值无法转换。例如，转换会截断数据。</p></td>
</tr>
<tr class="even">
<td><p><strong>adErrCantCreate</strong></p></td>
<td><p>3725<br />
-2146824563<br />
0x800A0E8D</p></td>
<td><p>因为字段数据类型未知，或提供程序没有足够的资源执行该操作，无法设置或检索数据值。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adErrCatalogNotSet</strong></p></td>
<td><p>3747<br />
-2146824541<br />
0x800A0EA3</p></td>
<td><p>操作需要一个有效的 <strong>ParentCatalog</strong> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>adErrColumnNotOnThisRow</strong></p></td>
<td><p>3726<br />
-2146824562<br />
0x800A0E8E</p></td>
<td><p>记录不包含此字段。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adErrDataConversion</strong></p></td>
<td><p>3421<br />
-2146824867<br />
0x800A0D5D</p></td>
<td><p>应用程序在当前操作中使用了错误类型的值。</p></td>
</tr>
<tr class="even">
<td><p><strong>adErrDataOverflow</strong></p></td>
<td><p>3721<br />
-2146824567<br />
0x800A0E89</p></td>
<td><p>数据值过大，无法以字段数据类型表示。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adErrDelResOutOfScope</strong></p></td>
<td><p>3738<br />
-2146824550<br />
0x800A0E9A</p></td>
<td><p>要被删除对象的 URL 超出了当前记录的范围。</p></td>
</tr>
<tr class="even">
<td><p><strong>adErrDenyNotSupported</strong></p></td>
<td><p>3750<br />
-2146824538<br />
0x800A0EA6</p></td>
<td><p>提供程序不支持共享限制。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adErrDenyTypeNotSupported</strong></p></td>
<td><p>3751<br />
-2146824537<br />
0x800A0EA7</p></td>
<td><p>提供程序不支持所请求的共享限制类型。</p></td>
</tr>
<tr class="even">
<td><p><strong>adErrFeatureNotAvailable</strong></p></td>
<td><p>3251<br />
-2146825037<br />
0x800A0CB3</p></td>
<td><p>对象或提供程序不能执行所需的操作。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adErrFieldsUpdateFailed</strong></p></td>
<td><p>3749<br />
-2146824539<br />
0x800A0EA5</p></td>
<td><p>字段更新失败。有关详细信息，请检查各个字段对象的 <strong>Status</strong> 属性。</p></td>
</tr>
<tr class="even">
<td><p><strong>adErrIllegalOperation</strong></p></td>
<td><p>3219<br />
-2146825069<br />
0x800A0C93</p></td>
<td><p>此上下文中不允许操作。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adErrIntegrityViolation</strong></p></td>
<td><p>3719<br />
-2146824569<br />
0x800A0E87</p></td>
<td><p>数据值与字段的完整性约束冲突。</p></td>
</tr>
<tr class="even">
<td><p><strong>adErrInTransaction</strong></p></td>
<td><p>3246<br />
-2146825042<br />
0x800A0CAE</p></td>
<td><p>在事务处理过程中，不能显式关闭 <strong>Connection</strong> 对象。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adErrInvalidArgument</strong></p></td>
<td><p>3001<br />
-2146825287<br />
0x800A0BB9</p></td>
<td><p>参数类型不正确，或不在可以接受的范围之内，或与其他参数冲突。</p></td>
</tr>
<tr class="even">
<td><p><strong>adErrInvalidConnection</strong></p></td>
<td><p>3709<br />
-2146824579<br />
0x800A0E7D</p></td>
<td><p>该连接无法用于执行此操作。它已关闭或在此上下文中无效。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adErrInvalidParamInfo</strong></p></td>
<td><p>3708<br />
-2146824580<br />
0x800A0E7C</p></td>
<td><p>没有正确定义 <strong>Parameter</strong> 对象。提供的信息不一致或不完整。  </p></td>
</tr>
<tr class="even">
<td><p><strong>adErrInvalidTransaction</strong></p></td>
<td><p>3714<br />
-2146824574<br />
0x800A0E82</p></td>
<td><p>协调事务无效或未开始。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adErrInvalidURL</strong></p></td>
<td><p>3729<br />
-2146824559<br />
0x800A0E91</p></td>
<td><p>URL 包含无效字符。请确保键入的 URL 正确。</p></td>
</tr>
<tr class="even">
<td><p><strong>adErrItemNotFound</strong></p></td>
<td><p>3265<br />
-2146825023<br />
0x800A0CC1</p></td>
<td><p>在对应于所请求的名称或序号的集合中没有找到项。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adErrNoCurrentRecord</strong></p></td>
<td><p>3021<br />
-2146825267<br />
0x800A0BCD</p></td>
<td><p><strong>BOF</strong> 或 <strong>EOF</strong> 为 True，或者当前记录已被删除。所请求的操作需要当前记录。</p></td>
</tr>
<tr class="even">
<td><p><strong>adErrNotExecuting</strong></p></td>
<td><p>3715<br />
-2146824573<br />
0x800A0E83</p></td>
<td><p>没有执行时，无法执行操作。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adErrNotReentrant</strong></p></td>
<td><p>3710<br />
-2146824578<br />
0x800A0E7E</p></td>
<td><p>在处理事件的过程中，无法执行操作。</p></td>
</tr>
<tr class="even">
<td><p><strong>adErrObjectClosed</strong></p></td>
<td><p>3704<br />
-2146824584<br />
0x800A0E78</p></td>
<td><p>对象关闭时不允许操作。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adErrObjectInCollection</strong></p></td>
<td><p>3367<br />
-2146824921<br />
0x800A0D27</p></td>
<td><p>对象已在集合中。不能追加。</p></td>
</tr>
<tr class="even">
<td><p><strong>adErrObjectNotSet</strong></p></td>
<td><p>3420<br />
-2146824868<br />
0x800A0D5C</p></td>
<td><p>对象不再有效。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adErrObjectOpen</strong></p></td>
<td><p>3705<br />
-2146824583<br />
0x800A0E79</p></td>
<td><p>对象打开时不允许操作。</p></td>
</tr>
<tr class="even">
<td><p><strong>adErrOpeningFile</strong></p></td>
<td><p>3002<br />
-2146825286<br />
0x800A0BBA</p></td>
<td><p>无法打开文件。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adErrOperationCancelled</strong></p></td>
<td><p>3712<br />
-2146824576<br />
0x800A0E80</p></td>
<td><p>操作已被用户取消。</p></td>
</tr>
<tr class="even">
<td><p><strong>adErrOutOfSpace</strong></p></td>
<td><p>3734<br />
-2146824554<br />
0x800A0E96</p></td>
<td><p>无法执行操作。提供程序无法获取足够的存储空间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adErrPermissionDenied</strong></p></td>
<td><p>3720<br />
-2146824568<br />
0x800A0E88</p></td>
<td><p>权限不足，阻止写入字段。</p></td>
</tr>
<tr class="even">
<td><p><strong>adErrProviderFailed</strong></p></td>
<td><p>3000<br />
-2146825288<br />
0x800A0BB8</p></td>
<td><p>提供程序未能执行请求的操作。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adErrProviderNotFound</strong></p></td>
<td><p>3706<br />
-2146824582<br />
0x800A0E7A</p></td>
<td><p>找不到提供程序。该程序可能未正确安装。</p></td>
</tr>
<tr class="even">
<td><p><strong>adErrReadFile</strong></p></td>
<td><p>3003<br />
-2146825285<br />
0x800A0BBB</p></td>
<td><p>无法读取文件。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adErrResourceExists</strong></p></td>
<td><p>3731<br />
-2146824557<br />
0x800A0E93</p></td>
<td><p>无法执行复制操作。由目标 URL 命名的对象已经存在。指定 <strong>adCopyOverwrite</strong> 替换该对象。</p></td>
</tr>
<tr class="even">
<td><p><strong>adErrResourceLocked</strong></p></td>
<td><p>3730<br />
-2146824558<br />
0x800A0E92</p></td>
<td><p>由指定的 URL 表示的对象被一个或多个其他进程锁定。请等待该进程完成，然后重试该操作。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adErrResourceOutOfScope</strong></p></td>
<td><p>3735<br />
-2146824553<br />
0x800A0E97</p></td>
<td><p>源 URL 或目标 URL 在当前记录的范围之外。</p></td>
</tr>
<tr class="even">
<td><p><strong>adErrSchemaViolation</strong></p></td>
<td><p>3722<br />
-2146824566<br />
0x800A0E8A</p></td>
<td><p>数据值与数据类型或字段的约束冲突。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adErrSignMismatch</strong></p></td>
<td><p>3723<br />
-2146824565<br />
0x800A0E8B</p></td>
<td><p>转换失败，原因是数据值有符号，而提供程序所使用的字段数据类型无符号。</p></td>
</tr>
<tr class="even">
<td><p><strong>adErrStillConnecting</strong></p></td>
<td><p>3713<br />
-2146824575<br />
0x800A0E81</p></td>
<td><p>在异步连接时，无法执行操作。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adErrStillExecuting</strong></p></td>
<td><p>3711<br />
-2146824577<br />
0x800A0E7F</p></td>
<td><p>在异步执行时，无法执行操作。</p></td>
</tr>
<tr class="even">
<td><p><strong>adErrTreePermissionDenied</strong></p></td>
<td><p>3728<br />
-2146824560<br />
0x800A0E90</p></td>
<td><p>权限不足，无法访问树或子树。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adErrUnavailable</strong></p></td>
<td><p>3736<br />
-2146824552<br />
0x800A0E98</p></td>
<td><p>操作未能完成，状态不可用。可能是字段不可用或未尝试任何操作。</p></td>
</tr>
<tr class="even">
<td><p><strong>adErrUnsafeOperation</strong></p></td>
<td><p>3716<br />
-2146824572<br />
0x800A0E84</p></td>
<td><p>此计算机上的安全设置禁止访问其他域上的数据源。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adErrURLDoesNotExist</strong></p></td>
<td><p>3727<br />
-2146824561<br />
0x800A0E8F</p></td>
<td><p>源 URL 或目标 URL 的父级不存在。</p></td>
</tr>
<tr class="even">
<td><p><strong>adErrURLNamedRowDoesNotExist</strong></p></td>
<td><p>3737<br />
-2146824551<br />
0x800A0E99</p></td>
<td><p>此 URL 指定的记录不存在。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adErrVolumeNotFound</strong></p></td>
<td><p>3733<br />
-2146824555<br />
0x800A0E95</p></td>
<td><p>提供程序找不到 URL 指定的存储设备。请确保键入的 URL 正确。</p></td>
</tr>
<tr class="even">
<td><p><strong>adErrWriteFile</strong></p></td>
<td><p>3004<br />
-2146825284<br />
0x800A0BBC</p></td>
<td><p>写入文件失败。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adWrnSecurityDialog</strong></p></td>
<td><p>3717<br />
-2146824571<br />
0x800A0E85</p></td>
<td><p>仅供内部使用。请勿使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>adWrnSecurityDialogHeader</strong></p></td>
<td><p>3718<br />
-2146824570<br />
0x800A0E86</p></td>
<td><p>仅供内部使用。请勿使用。</p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a>ADO/WFC 等效值

包： **com.ms.wfc.data**

仅定义了 ADO/WFC 等效值的以下子集。

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>常量</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AdoEnums.ErrorValue.BOUNDTOCOMMAND</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.ErrorValue.DATACONVERSION</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.ErrorValue.FEATURENOTAVAILABLE</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.ErrorValue.ILLEGALOPERATION</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.ErrorValue.INTRANSACTION</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.ErrorValue.INVALIDARGUMENT</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.ErrorValue.INVALIDCONNECTION</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.ErrorValue.INVALIDPARAMINFO</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.ErrorValue.ITEMNOTFOUND</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.ErrorValue.NOCURRENTRECORD</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.ErrorValue.NOTEXECUTING</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.ErrorValue.NOTREENTRANT</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.ErrorValue.OBJECTCLOSED</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.ErrorValue.OBJECTINCOLLECTION</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.ErrorValue.OBJECTNOTSET</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.ErrorValue.OBJECTOPEN</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.ErrorValue.OPERATIONCANCELLED</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.ErrorValue.PROVIDERNOTFOUND</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.ErrorValue.STILLCONNECTING</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.ErrorValue.STILLEXECUTING</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.ErrorValue.UNSAFEOPERATION</p></td>
</tr>
</tbody>
</table>

