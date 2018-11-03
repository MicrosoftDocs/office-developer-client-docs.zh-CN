---
title: 初始化 Microsoft Exchange 数据源驱动程序
TOCTitle: Initializing the Microsoft Exchange Data Source Driver
ms:assetid: cf87a746-f846-1a01-f4ec-20a25e335193
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834677(v=office.15)
ms:contentKeyID: 48547810
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- acmain11.chm1032667
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 6e1d61d2f61050118745347441cba1f27c35c41f
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25937741"
---
# <a name="initializing-the-microsoft-exchange-data-source-driver"></a>初始化 Microsoft Exchange 数据源驱动程序

**适用于**： Access 2013、 Office 2013

当您安装 Microsoft Exchange 数据源驱动程序时，安装程序会将一组默认值写入 Microsoft Windows 注册表中的引擎和 ISAM 格式的子项。 不应直接修改这些设置，而应使用应用程序的安装程序来添加、删除或更改这些设置。 以下各节说明了 Microsoft Exchange 数据源驱动程序的初始化及 ISAM 格式设置。

## <a name="microsoft-exchange-data-source-initialization-settings"></a>Microsoft Exchange 数据源初始化设置

**Access Connectivity 引擎\\引擎\\Exchange**文件夹包括 Aceexch.dll 驱动程序，用于外部访问 Microsoft Outlook 和 Microsoft Exchange 文件夹的初始化设置。 此文件夹中的唯一一项如下所示：

`win32=<path>\ACEEXCH.DLL`

Microsoft Access 数据库引擎使用此设置指定 Aceexch.dll 的位置。 其完整路径在安装时确定。 注册表类型的值为\_SZ。

使用 Outlook ISAM 格式和使用 Exchange 客户端 ISAM 格式的效果相似。唯一的区别在于两个不同的客户端为同一列指定不同的名称。这两种 ISAM 格式都已创建，以便 Microsoft Access 数据库引擎能够按用户所需的样式返回列名。

## <a name="microsoft-outlook-client-isam-formats"></a>Microsoft Outlook 客户端 ISAM 格式

**Access Connectivity 引擎\\ISAM 格式\\Outlook 9.0**文件夹包含下列项。

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
<td><p>Outlook()</p></td>
</tr>
<tr class="odd">
<td><p>CanLink</p></td>
<td><p>REG_BINARY</p></td>
<td><p>01</p></td>
</tr>
<tr class="even">
<td><p>OneTablePerFile</p></td>
<td><p>REG_BINARY</p></td>
<td><p>00</p></td>
</tr>
<tr class="odd">
<td><p>IsamType</p></td>
<td><p>REG_DWORD</p></td>
<td><p>3</p></td>
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
<td><p>01</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> [!注释] 更改 Windows 注册表设置后，必须退出并重新启动数据库引擎，以使新的设置生效。



## <a name="microsoft-exchange-client-isam-formats"></a>Microsoft Exchange 客户端 ISAM 格式

**Access Connectivity 引擎\\ISAM 格式\\Exchange 4.0**文件夹包含下列项。

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
<td><p>Exchange()</p></td>
</tr>
<tr class="odd">
<td><p>CanLink</p></td>
<td><p>REG_BINARY</p></td>
<td><p>01</p></td>
</tr>
<tr class="even">
<td><p>OneTablePerFile</p></td>
<td><p>REG_BINARY</p></td>
<td><p>00</p></td>
</tr>
<tr class="odd">
<td><p>IsamType</p></td>
<td><p>REG_DWORD</p></td>
<td><p>3</p></td>
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
<td><p>01</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> [!注释] 更改 Windows 注册表设置后，必须退出并重新启动数据库引擎，以使新的设置生效。



## <a name="customizing-the-schemaini-file-for-outlook-and-exchange-data"></a>为 Outlook 和 Exchange 数据自定义 Schema.ini 文件

Outlook 和 Exchange ISAM 使用 Schema.ini 文件的方式类似于 Text ISAM 使用它的方式。Schema.ini 包含数据源的特定信息：数据的格式以及需要进行访问的列的名称。

在读取、导入或导出 Outlook 和 Exchange 的数据前，没有必要修改 Schema.ini 文件。Schema.ini 文件中的许多用于 Outlook 和 Exchange 的设置是针对于 MAPI 所需的内部标记的。不要尝试修改这些标记值。

