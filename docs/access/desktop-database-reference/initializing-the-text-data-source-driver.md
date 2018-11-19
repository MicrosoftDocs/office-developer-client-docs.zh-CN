---
title: 初始化文本数据源驱动程序
TOCTitle: Initializing the Text Data Source driver
ms:assetid: cba0864e-5f94-bf43-4708-b1981e3acaff
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834391(v=office.15)
ms:contentKeyID: 48547718
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- acmain11.chm1032166
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 9b240dbf55d2907b24b47349ee56e492f7d5e08d
ms.sourcegitcommit: 45feafb3b55de0402dddf5548c0c1c43a0eabafd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "26026461"
---
# <a name="initializing-the-text-data-source-driver"></a>初始化文本数据源驱动程序

**适用于**： Access 2013、 Office 2013

使用相同的数据库驱动因素为两个文本数据源和 HTML 数据源。

当您安装的文本数据源数据库驱动程序时，安装程序会将一组默认值写入 Microsoft Windows 注册表中的引擎和 ISAM 格式子项。 不应直接修改这些设置，而应使用应用程序的安装程序来添加、删除或更改这些设置。 以下各节说明了文本数据源数据库驱动程序的初始化和 ISAM 格式设置。

## <a name="text-data-source-initialization-settings"></a>文本数据源初始化设置

**Access Connectivity 引擎\\ISAM 格式\\文本文件夹**包括 Acetxt.dll 驱动程序，用于对文本数据文件的外部访问的初始化设置。 下面的示例显示了此文件夹中各项的典型设置。

```vb
    win32=<path>\ ACETXT.DLL 
    
    MaxScanRows=25 
    
    FirstRowHasNames=True 
    
    CharacterSet= ANSI 
    
    Format=CSVDelimited 
    
    Extensions= txt,csv,tab,asc 
    
    ExportCurrencySymbols=Yes
```

<br/>

Microsoft Access 数据库引擎使用如下所示的 Text 文件夹项。

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
<td><p>win32</p></td>
<td><p>Acetxt.dll 的位置。完整路径在安装时确定。值为 REG_SZ 类型。</p></td>
</tr>
<tr class="even">
<td><p>MaxScanRows</p></td>
<td><p>推测列类型时要扫描的行数。如果设为 0，则搜索整个文件。默认值为 25。值为 REG_DWORD 类型。</p></td>
</tr>
<tr class="odd">
<td><p>FirstRowHasNames</p></td>
<td><p>二进制值，指示表的第一行是否包含列名称。值 01 指示在导入期间从第一行获取列名称。</p></td>
</tr>
<tr class="even">
<td><p>CharacterSet</p></td>
<td><p>指示文本页存储方式的指示器，可能的设置有：</p>
<p></p>
<ul>
<li><p>ANSI - 计算机的 ANSI 代码页。AnsiToUnicode 和 UnicodeToAnsi 转换已完成。</p></li>
<li><p>OEM - 计算机的 OEM 代码页。OemToUnicode 和 UnicodeToOem 转换已完成。</p></li>
<li><p>Unicode - 代码页转换未完成。</p></li>
<li><p>&lt;十进制数&gt;— 特定字符集的代码页号。 将完成转换与 Unicode。</p></li>
</ul>
<p></p>
<p>默认值为 ANSI。值为 REG_SZ 类型。</p></td>
</tr>
<tr class="odd">
<td><p>Format</p></td>
<td><p>可以是以下任一： TabDelimited，CSVDelimited，带分隔符 (&lt;单个字符&gt;)。 带分隔符格式的单字符分隔符可以是任意单个字符除外双引号 (&quot;)。 默认值为 CSVDelimited。 值为 REG_SZ 类型。</p></td>
</tr>
<tr class="even">
<td><p>Extensions</p></td>
<td><p>查找基于文本的数据时将要浏览的任何文件的扩展名。默认值为 txt、csv、tab、asc。值为 REG_SZ 类型。</p></td>
</tr>
<tr class="odd">
<td><p>ExportCurrencySymbols</p></td>
<td><p>二进制值，指示导出货币字段时是否包括适当的货币符号。值 01 指示包括该符号，值 00 指示只导出数值数据。默认值为 01。值为 REG_BINARY 类型。</p></td>
</tr>
</tbody>
</table>


## <a name="text-data-source-isam-formats"></a>文本数据源 ISAM 格式

**Access Connectivity 引擎\\ISAM 格式\\文本**文件夹包含下列项。

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
<td><p>文本</p></td>
</tr>
<tr class="even">
<td><p>ExportFilter</p></td>
<td><p>REG_SZ</p></td>
<td><p>文本文件（*.txt、*.csv、*.tab、*.asc）</p></td>
</tr>
<tr class="odd">
<td><p>ImportFilter</p></td>
<td><p>REG_SZ</p></td>
<td><p>文本文件（*.txt、*.csv、*.tab、*.asc）</p></td>
</tr>
<tr class="even">
<td><p>CanLink</p></td>
<td><p>REG_BINARY</p></td>
<td><p>01</p></td>
</tr>
<tr class="odd">
<td><p>OneTablePerFile</p></td>
<td><p>REG_BINARY</p></td>
<td><p>01</p></td>
</tr>
<tr class="even">
<td><p>IsamType</p></td>
<td><p>REG_DWORD</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>IndexDialog</p></td>
<td><p>REG_BINARY</p></td>
<td><p>00</p></td>
</tr>
<tr class="even">
<td><p>CreateDBOnExport</p></td>
<td><p>REG_BINARY</p></td>
<td><p>00</p></td>
</tr>
<tr class="odd">
<td><p>ResultTextImport</p></td>
<td><p>REG_SZ</p></td>
<td><p>从外部文件向当前数据库导入数据。更改当前数据库中的数据时不会更改外部文件中的数据。</p></td>
</tr>
<tr class="even">
<td><p>ResultTextLink</p></td>
<td><p>REG_SZ</p></td>
<td><p>在与外部文件链接的当前数据库中创建表。更改当前数据库中的数据将会更改外部文件中的数据。</p></td>
</tr>
<tr class="odd">
<td><p>ResultTextExport</p></td>
<td><p>REG_SZ</p></td>
<td><p>将数据从当前数据库导出到文本文件。如果导出到现有文件，此过程将覆盖数据。</p></td>
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

## <a name="html-import-isam-formats"></a>HTML 导入 ISAM 格式

**Access Connectivity 引擎\\ISAM 格式\\HTML 导入**文件夹包含下列项。

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
<td><p>文本</p></td>
</tr>
<tr class="even">
<td><p>ImportFilter</p></td>
<td><p>REG_SZ</p></td>
<td><p>HTML 文件 (*.ht **)</p></td>
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
<td><p>2</p></td>
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
<td><p>ResultTextImport</p></td>
<td><p>REG_SZ</p></td>
<td><p>从外部文件向当前数据库导入数据。更改当前数据库中的数据时不会更改外部文件中的数据。</p></td>
</tr>
<tr class="odd">
<td><p>ResultTextLink</p></td>
<td><p>REG_SZ</p></td>
<td><p>在与外部文件链接的当前数据库中创建表。更改当前数据库中的数据将会更改外部文件中的数据。</p></td>
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

## <a name="html-export-isam-formats"></a>HTML 导出 ISAM 格式

**Access Connectivity 引擎\\ISAM 格式\\HTML 导出**文件夹包含下列项。

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
<td><p>文本</p></td>
</tr>
<tr class="even">
<td><p>ExportFilter</p></td>
<td><p>REG_SZ</p></td>
<td><p>HTML 文件 (*.htm)</p></td>
</tr>
<tr class="odd">
<td><p>CanLink</p></td>
<td><p>REG_BINARY</p></td>
<td><p>00</p></td>
</tr>
<tr class="even">
<td><p>OneTablePerFile</p></td>
<td><p>REG_BINARY</p></td>
<td><p>01</p></td>
</tr>
<tr class="odd">
<td><p>IsamType</p></td>
<td><p>REG_DWORD</p></td>
<td><p>2</p></td>
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
<td><p>ResultTextExport</p></td>
<td><p>REG_SZ</p></td>
<td><p>将数据从当前数据库导出到文本文件。如果导出到现有文件，此过程将覆盖数据。</p></td>
</tr>
<tr class="odd">
<td><p>SupportsLongNames</p></td>
<td><p>REG_BINARY</p></td>
<td><p>01</p></td>
</tr>
</tbody>
</table>

> [!NOTE]
> [!注释] 更改 Windows 注册表设置后，必须退出并重新启动数据库引擎，以使新的设置生效。

## <a name="customizing-the-schemaini-file-for-text-and-html-data"></a>自定义文本和 HTML 数据的 Schema.ini 文件

若要读取、导入或导出文本和 HTML 数据，除要在 .ini 文件中包括文本 ISAM 信息外，还需要创建 Schema.ini 文件。Schema.ini 包含数据源的结构信息：如何设置文本文件的格式、如果在导入时读取文本文件、文件的默认导出格式是什么。下面的示例显示了定宽文件 Filename.txt 的布局：

```text
    [Filename.txt] 
    
    ColNameHeader=False 
    
    Format=FixedLength 
    
    FixedFormat= RaggedEdge 
    
    MaxScanRows=25 
    
    CharacterSet=OEM 
    
    Col1=columnname Char Width 24 
    
    Col2=columnname2 Date Width 9 
    
    Col3=columnname7 Float Width 10 
    
    Col4=columnname8 Integer Width 10 
    Col5=columnname9 LongChar Width 10
```

<br/>

类似地，分隔文件的格式按如下所示进行指定：

```text
    [Delimit.txt] 
    
    ColNameHeader=True 
    
    Format=Delimited() 
    
    MaxScanRows=0 
    
    CharacterSet=OEM 
    
    Col1=username char width 50 
    
    Col2=dateofbirth Date width 9
```

<br/>

如果要将数据导出到分隔文本文件中，还要指定该文件的格式：

```text
    [Export: My Special Export] 
    
    ColNameHeader=True 
    
    Format=TabDelimited 
    
    MaxScanRows=25 
    
    CharacterSet=OEM 
    
    DateTimeFormat=mm.dd.yy.hh.mm.ss 
    
    CurrencySymbol=Dm 
    
    CurrencyPosFormat=0 
    
    CurrencyDigits=2 
    
    CurrencyNegFormat=0 
    
    CurrencyThousandSymbol=, 
    
    CurrencyDecimalSymbol=. 
    
    DecimalSymbol=, 
    
    NumberDigits=2 
    
    NumberLeadingZeros=0 
    
    TextDelimeter="
```

<br/>

"My Special Export"示例引用了特定导出选项。可以在连接时指定任何不同的导出选项。最后一个示例还对应于在连接时可选要传递的数据源名称 (DSN)。所有这三个格式部分都可以包括在同一个 .ini 文件中。

Microsoft Access 数据库引擎使用如下所示的 Schema.ini 项。

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
<td><p>ColNameHeader</p></td>
<td><p>可设为 <strong>True</strong>（指示由第一条数据记录指定列的名称）或 <strong>False</strong>。</p></td>
</tr>
<tr class="even">
<td><p>Format</p></td>
<td><p>可以将设置为下列值之一： TabDelimited，CSVDelimited，带分隔符 (&lt;单个字符&gt;)，或 FixedLength。 指定分隔符号文件格式可以是除双引号之外的任何单个字符的分隔符 (&quot;)。</p></td>
</tr>
<tr class="odd">
<td><p>FixedFormat</p></td>
<td><p>仅在 Format 为 FixedLength 时使用，此项可以设为下列值之一：RaggedEdge 或 TrueFixedLength。
 RaggedEdge 允许行以回车符终止。 TrueFixedLength 要求每一行都是确切的字符数，并且假定不在行边界的任何回车符都嵌入在字段中。 如果没有此设置，默认值为 RaggedEdge。</p></td>
</tr>
<tr class="even">
<td><p>MaxScanRows</p></td>
<td><p>指示在推测列数据类型时要扫描的行数。如果设为 0，则搜索整个文件。</p></td>
</tr>
<tr class="odd">
<td><p>CharacterSet</p></td>
<td><p>可设为 OEM、ANSI、UNICODE 或有效代码页的十进制数，指示源文件的字符集。</p></td>
</tr>
<tr class="even">
<td><p>DateTimeFormat</p></td>
<td><p>可设为指示日期和时间的格式字符串。如果导入/导出时的所有日期/时间字段均用相同格式处理，则应指定此项。除 AM 和 PM 以外，所有 Microsoft Jet 数据库引擎格式均受支持。如果没有格式字符串，则使用 Windows“控制面板”的短日期图片和时间选项。</p></td>
</tr>
<tr class="odd">
<td><p>CurrencySymbol</p></td>
<td><p>指示文本文件中的货币值要使用的货币符号。例如，美元符号 ($) 和德国马克。如果没有此项，则使用 Windows 控制面板中的默认值。</p></td>
</tr>
<tr class="even">
<td><p>CurrencyPosFormat</p></td>
<td><p>可设为以下值之一： 与没有分离 ($1) 货币符号后缀没有分隔的货币符号前缀 (1$) 与一个字符分隔 ($ 1) 货币符号后缀用一个字符分隔的货币符号前缀 (1 $) 如果此条目不存在，使用 Windows 控制面板中的默认值。</p></td>
</tr>
<tr class="odd">
<td><p>CurrencyDigits</p></td>
<td><p>指定货币数额的小数部分使用的数字位数。如果没有此项，则使用 Windows 控制面板中的默认值。</p></td>
</tr>
<tr class="even">
<td><p>CurrencyNegFormat</p></td>
<td><p>可以是下列值之一: ($1) – $1 $– 1 $1 – (1$) – 1$ 1 – 1$ – – 1 $ – $ 1 1 $– $ 1 – $ – 1 1 – $ ($ 1) (1 $) 此示例中，为了显示美元符号，但它应替换为实际的程序中的相应 CurrencySymbol 值。 如果没有此项，则使用 Windows 控制面板中的默认值。</p></td>
</tr>
<tr class="odd">
<td><p>CurrencyThousandSymbol</p></td>
<td><p>指示用于在文本文件中按千分隔货币值的单字符符号。如果没有此项，则使用 Windows 控制面板中的默认值。</p></td>
</tr>
<tr class="even">
<td><p>CurrencyDecimalSymbol</p></td>
<td><p>可设为用于分隔货币数额的整数部分和小数部分的任何单字符。如果没有此项，则使用 Windows 控制面板中的默认值。</p></td>
</tr>
<tr class="odd">
<td><p>DecimalSymbol</p></td>
<td><p>可设为用于分隔数字的整数部分和小数部分的任何单字符。如果没有此项，则使用 Windows 控制面板中的默认值。</p></td>
</tr>
<tr class="even">
<td><p>NumberDigits</p></td>
<td><p>指示数字的小数部分的小数位数。如果没有此项，则使用 Windows 控制面板中的默认值。</p></td>
</tr>
<tr class="odd">
<td><p>NumberLeadingZeros</p></td>
<td><p>指定大于 -1 但小于 1 的小数值是否应包含几个前导零。该值可以为 False（没有前导零）或 True。</p></td>
</tr>
<tr class="even">
<td><p>Col1、Col2 …</p></td>
<td><p>列出要读取的文本文件中的列。 此项的格式应为： <em>Coln</em>=<em>columnName</em>类型 [宽度<em>#</em>] <em>columnName</em>： 具有嵌入空格的列名称应括在引号中。 <em>类型</em>： 可以是位、 Byte、 短、 Long、 Decimal、 货币、 单个、 Double，DateTime。 二进制，OLE、 文本或备注。 此外，支持下列 ODBC 文本驱动程序类型： 对于在 Memo 类型可以是一个附加格式标记 [Attribute Hyperlink] Char （同 Text） Float （同 Double） Integer （同 Short） longchar （同备注） 于日期<em>日期格式</em>用于指定应在 Microsoft Access 中的活动 Url 的列。 在 Decimal 类型的情况下，应使用附加格式标记 [Scale #] Precision #]。</p></td>
</tr>
<tr class="odd">
<td><p>TextDelimiter</p></td>
<td><p>可设为用于对包含任何其他特殊字符的字符串进行分隔的任何单字符。
 例如， &quot;abc&quot;，&quot;xyz，pqr&quot;，&quot;hij&quot;如果不存在此条目的默认分隔符为双引号。 如果此条目是字符串&quot;无&quot;，然后没有字符将被视为分隔符。</p></td>
</tr>
</tbody>
</table>

> [!NOTE]
> [!注释] 更改 Schema.ini 文件设置时，必须先退出数据库引擎，然后再重新启动它，这样，新设置才会生效。


