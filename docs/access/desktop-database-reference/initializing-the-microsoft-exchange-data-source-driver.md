---
title: 初始化 Microsoft Exchange 数据源驱动程序
TOCTitle: Initializing the Microsoft Exchange Data Source driver
ms:assetid: cf87a746-f846-1a01-f4ec-20a25e335193
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834677(v=office.15)
ms:contentKeyID: 48547810
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- acmain11.chm1032667
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: b3460786785ae7b21184b6d96384ecc59e89d287
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291405"
---
# <a name="initializing-the-microsoft-exchange-data-source-driver"></a>初始化 Microsoft Exchange 数据源驱动程序

**适用于**：Access 2013、Office 2013

当您安装 microsoft Exchange 数据源驱动程序时, 安装程序会将一组默认值写入 "引擎" 和 "ISAM Formats" 子项中的 Microsoft Windows 注册表。 不应直接修改这些设置，而应使用应用程序的安装程序来添加、删除或更改这些设置。 以下各节说明了 Microsoft Exchange 数据源驱动程序的初始化及 ISAM 格式设置。

## <a name="microsoft-exchange-data-source-initialization-settings"></a>Microsoft Exchange 数据源初始化设置

**访问连接引擎\\引擎\\"Exchange**文件夹" 包括 Aceexch 驱动程序的初始化设置, 用于对 microsoft Outlook 和 microsoft Exchange 文件夹的外部访问。 此文件夹中的唯一一项如下所示：

`win32=<path>\ACEEXCH.DLL`

Microsoft Access 数据库引擎使用此设置指定 Aceexch.dll 的位置。 其完整路径在安装时确定。 值的类型为 REG\_SZ。

使用 Outlook ISAM 格式和使用 Exchange 客户端 ISAM 格式的效果相似。唯一的区别在于两个不同的客户端为同一列指定不同的名称。这两种 ISAM 格式都已创建，以便 Microsoft Access 数据库引擎能够按用户所需的样式返回列名。

## <a name="microsoft-outlook-client-isam-formats"></a>Microsoft Outlook 客户端 ISAM 格式

**Access Connectivity Engine\\ISAM 格式\\Outlook 9.0**文件夹包含以下项。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>项名</p></th>
<th><p>类型</p></th>
<th><p>值</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Engine</p></td>
<td><p>REG_SZ</p></td>
<td><p>Exchange</p></td>
</tr>
<tr class="even">
<td><p>ImportFilter</p></td>
<td><p>REG_SZ</p></td>
<td><p>Outlook ()</p></td>
</tr>
<tr class="odd">
<td><p>CanLink</p></td>
<td><p>REG_BINARY</p></td>
<td><p>前面</p></td>
</tr>
<tr class="even">
<td><p>OneTablePerFile</p></td>
<td><p>REG_BINARY</p></td>
<td><p>00</p></td>
</tr>
<tr class="odd">
<td><p>IsamType</p></td>
<td><p>REG_DWORD</p></td>
<td><p>第三章</p></td>
</tr>
<tr class="even">
<td><p>IndexDialog</p></td>
<td><p>REG_BINARY</p></td>
<td><p>00</p></td>
</tr>
<tr class="odd">
<td><p>CreateDBOnExport</p></td>
<td><p>REG_BINARY</p></td>
<td><p>00</p></td>
</tr>
<tr class="even">
<td><p>SupportsLongNames</p></td>
<td><p>REG_BINARY</p></td>
<td><p>前面</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> [!注释] 更改 Windows 注册表设置后，必须退出并重新启动数据库引擎，以使新的设置生效。



## <a name="microsoft-exchange-client-isam-formats"></a>Microsoft Exchange 客户端 ISAM 格式

**Access Connectivity Engine\\ISAM 格式\\Exchange 4.0**文件夹包含以下项。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>项名</p></th>
<th><p>类型</p></th>
<th><p>值</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Engine</p></td>
<td><p>REG_SZ</p></td>
<td><p>Exchange</p></td>
</tr>
<tr class="even">
<td><p>ImportFilter</p></td>
<td><p>REG_SZ</p></td>
<td><p>Exchange ()</p></td>
</tr>
<tr class="odd">
<td><p>CanLink</p></td>
<td><p>REG_BINARY</p></td>
<td><p>前面</p></td>
</tr>
<tr class="even">
<td><p>OneTablePerFile</p></td>
<td><p>REG_BINARY</p></td>
<td><p>00</p></td>
</tr>
<tr class="odd">
<td><p>IsamType</p></td>
<td><p>REG_DWORD</p></td>
<td><p>第三章</p></td>
</tr>
<tr class="even">
<td><p>IndexDialog</p></td>
<td><p>REG_BINARY</p></td>
<td><p>00</p></td>
</tr>
<tr class="odd">
<td><p>CreateDBOnExport</p></td>
<td><p>REG_BINARY</p></td>
<td><p>00</p></td>
</tr>
<tr class="even">
<td><p>SupportsLongNames</p></td>
<td><p>REG_BINARY</p></td>
<td><p>前面</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> [!注释] 更改 Windows 注册表设置后，必须退出并重新启动数据库引擎，以使新的设置生效。



## <a name="customizing-the-schemaini-file-for-outlook-and-exchange-data"></a>自定义 Outlook 和 Exchange 数据的 schema.ini 文件

Outlook 和 Exchange ISAM 使用 Schema.ini 文件的方式类似于 Text ISAM 使用它的方式。Schema.ini 包含数据源的特定信息：数据的格式以及需要进行访问的列的名称。

在读取、导入或导出 Outlook 和 Exchange 的数据前，没有必要修改 Schema.ini 文件。Schema.ini 文件中的许多用于 Outlook 和 Exchange 的设置是针对于 MAPI 所需的内部标记的。不要尝试修改这些标记值。

