---
title: 初始化 Microsoft Excel 驱动程序
TOCTitle: Initializing the Microsoft Excel driver
ms:assetid: 06c7f823-8e74-0811-cc00-e6b32075ef11
ms:mtpsurl: https://msdn.microsoft.com/library/Ff844939(v=office.15)
ms:contentKeyID: 48543054
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- acmain11.chm1032159
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 2fe59f34c04314f70117b3bc7f08d78c2d23ae6d
ms.sourcegitcommit: 62228a65109a9543cd223dfbf326dbf1af256748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "30179661"
---
# <a name="initializing-the-microsoft-excel-driver"></a>初始化 Microsoft Excel 驱动程序

**适用**于: Access 2013 |Office 2013

安装 Excel 驱动程序时, 安装程序会将一组默认值写入 "引擎" 和 "ISAM Formats" 子项中的 Windows 注册表中。 不应直接修改这些设置，而应使用应用程序的安装程序来添加、删除或更改这些设置。 以下各节说明了 Microsoft Excel 数据库驱动程序的初始化和 ISAM 格式设置。

## <a name="excel-initialization-settings"></a>Excel 初始化设置

**Access Connectivity Engine Engine\\\\Excel**文件夹包括用于对 Microsoft Excel 工作表进行外部访问的 Aceexcl 驱动程序的初始化设置。 下面的示例显示了此文件夹中各项的典型设置。

```vb
    win32=<path>\ Aceexcl.dll  
    
    TypeGuessRows=8 
    
    ImportMixedTypes=Text 
    
    AppendBlankRows=1 
    
    FirstRowHasNames=Yes
```

Microsoft Access 数据库引擎使用如下所示的 Excel 文件夹项。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>项</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>32</p></td>
<td><p>msexcl40.dll 的位置。完整路径在安装时确定。值为 REG_SZ 类型。</p></td>
</tr>
<tr class="even">
<td><p>TypeGuessRows</p></td>
<td><p>确定数据类型时需要检查的行数。数据类型根据找到的数据种类的最大数目确定。如果这样做无效，则按如下顺序确定数据类型：数字、货币、日期、文本、布尔。如果遇到的数据与所猜测的列数据类型不匹配，该数据将作为 <strong>Null</strong> 值返回。在导入时，如果某列使用混合数据类型，则整个列将根据 ImportMixedTypes 设置转换数据类型。 需要检查的默认行数为 8 行。值的类型为 REG_DWORD。  </p></td>
</tr>
<tr class="odd">
<td><p>ImportMixedTypes</p></td>
<td><p>可设为"MajorityType"或"Text"。如果设为"MajorityType"，混合数据类型的列在导入时将强制转换为占优势地位的数据类型。如果设为"Text"，混合数据类型的列在导入时将强制转换为"Text"。默认设置是"Text"。值为 REG_SZ 类型。</p></td>
</tr>
<tr class="even">
<td><p>AppendBlankRows</p></td>
<td><p>在添加新数据前，将追加到 3.5 版或 4.0 版工作表末尾的空白行数。例如，如果 AppendBlankRows 设为 4，Microsoft Jet 将在向工作表追加包含数据的行之前先追加 4 个空白行。此设置的整数值范围可以从 0 到 16。默认值为 01（追加一个附加行）。值为 REG_DWORD 类型。</p></td>
</tr>
<tr class="odd">
<td><p>FirstRowHasNames</p></td>
<td><p>指示表的第一行是否包含列名称的二进制值。值 01 指示在导入期间从第一行获取列名称。值 00 指示第一行中没有列名称。列名称显示为 F1、F2、F3 等。默认值为 01。值为 REG_BINARY 类型。</p></td>
</tr>
</tbody>
</table>

<br/>

**Access Connectivity Engine\\引擎\\Excel 8.0**文件夹包含以下项, 这些项适用于 Microsoft Excel 97。

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
<td><p>Excel</p></td>
</tr>
<tr class="even">
<td><p>ExportFilter</p></td>
<td><p>REG_SZ</p></td>
<td><p>Microsoft Excel 97-2000 (*.xls)</p></td>
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
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>IndexDialog</p></td>
<td><p>REG_BINARY</p></td>
<td><p>00</p></td>
</tr>
<tr class="odd">
<td><p>CreateDBOnExport</p></td>
<td><p>REG_BINARY</p></td>
<td><p>前面</p></td>
</tr>
<tr class="even">
<td><p>ResultTextExport</p></td>
<td><p>REG_SZ</p></td>
<td><p>将数据从当前数据库导出到 Microsoft Excel 97 文件。如果导出到现有文件，此过程将覆盖数据。</p></td>
</tr>
<tr class="odd">
<td><p>SupportsLongNames</p></td>
<td><p>REG_BINARY</p></td>
<td><p>前面</p></td>
</tr>
</tbody>
</table>

## <a name="using-the-typeguessrows-setting-for-excel-driver"></a>使用 Excel 驱动程序的 TypeGuessRows 设置
使用 Microsoft Excel 驱动程序时, 可以使用**TypeGuessRows**注册表值来配置要检查的数据类型的行数。 **TypeGuessRows**值位于以下注册表子项下:

# <a name="office-2016taboffice-2016"></a>[Office 2016](#tab/office-2016)

对于 MSI 安装的 Office

- 对于在 64 windows 上的32位或64位的 office 上为32位的 office, 请执行以下操作:
    
  **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\16.0\Access 连接 Engine\Engines\Excel**

- 对于64位 Windows 上的32位 Office:

  **HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Office\16.0\Access 连接 Engine\Engines\Excel**
    
对于 Office 即点即用安装

- 对于在 64 windows 上的32位或64位的 office 上为32位的 office, 请执行以下操作:
    
  **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\ClickToRun\REGISTRY\MACHINE\Software\Microsoft\Office\16.0\Access 连接 Engine\Engines\Excel**

- 对于64位 Windows 上的32位 Office:
    
  **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\ClickToRun\REGISTRY\MACHINE\Software\Wow6432Node\Microsoft\Office\16.0\Access 连接 Engine\Engines\Excel**

要检查的默认行数为**8** (八)。 当您将**TypeGuessRows**值设置为**0** (零) 时, Excel 驱动程序将检查数据类型的前16384行。 如果要检查16384以上的行, 请将**TypeGuessRows**设置为基于所需区域的值。 若要检查所有行, 请将**TypeGuessRows**设置为 1048576 (Excel 中允许的最大行数)。
 
数据类型由找到的最大数据类型数决定。 如果有关联, 则按以下顺序确定数据类型:

- 数字
- 货币
- Date
- 文本
- 布尔

如果遇到与列的猜测数据类型不匹配的数据, 则该数据以**Null**值的形式返回。 在导入过程中, 如果某一列具有混合的数据类型, 则整个列将转换为**ImportMixedTypes**设置所设置的数据类型。

# <a name="office-2013taboffice-2013"></a>[Office 2013](#tab/office-2013)

对于在 64 windows 上的32位或64位的 office 上为32位的 office, 请执行以下操作:

**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Access 连接 Engine\Engines\Excel**

对于64位 Windows 上的32位 Office:

**HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Office\15.0\Access 连接 Engine\Engines\Excel**

要检查的默认行数为**8** (八)。 当您将**TypeGuessRows**值设置为**0** (零) 时, Excel 驱动程序将检查数据类型的前16384行。 如果要检查16384以上的行, 请将**TypeGuessRows**设置为基于所需区域的值。 若要检查所有行, 请将**TypeGuessRows**设置为 1048576 (Excel 中允许的最大行数)。
 
数据类型由找到的最大数据类型数决定。 如果有关联, 则按以下顺序确定数据类型:

- 数字
- 货币
- Date
- 文本
- 布尔

如果遇到与列的猜测数据类型不匹配的数据, 则该数据以**Null**值的形式返回。 在导入过程中, 如果某一列具有混合的数据类型, 则整个列将转换为**ImportMixedTypes**设置所设置的数据类型。

# <a name="office-2010taboffice-2010"></a>[Office 2010](#tab/office-2010)

对于在 64 windows 上的32位或64位的 office 上为32位的 office, 请执行以下操作:

**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Access 连接 Engine\Engines\Excel**

对于64位 Windows 上的32位 Office:

**HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Office\15.0\Access 连接 Engine\Engines\Excel**

要检查的默认行数为**8** (八)。 当您将**TypeGuessRows**值设置为**0** (零) 时, Excel 驱动程序将检查数据类型的前16384行。 如果要检查16384以上的行, 请将**TypeGuessRows**设置为基于所需区域的值。 若要检查所有行, 请将**TypeGuessRows**设置为 1048576 (Excel 中允许的最大行数)。
 
数据类型由找到的最大数据类型数决定。 如果有关联, 则按以下顺序确定数据类型:

- 数字
- 货币
- Date
- 文本
- 布尔

如果遇到与列的猜测数据类型不匹配的数据, 则该数据以**Null**值的形式返回。 在导入过程中, 如果某一列具有混合的数据类型, 则整个列将转换为**ImportMixedTypes**设置所设置的数据类型。

---
> [!NOTE]
> [!注释] 更改 Windows 注册表设置后，必须退出并重新启动数据库引擎，以使新的设置生效。

