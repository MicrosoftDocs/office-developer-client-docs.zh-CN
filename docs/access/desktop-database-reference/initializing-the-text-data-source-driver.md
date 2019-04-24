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
localization_priority: Normal
ms.openlocfilehash: 2e76cc7d6b5254f2347e2264b0588ee1df643d05
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291419"
---
# <a name="initializing-the-text-data-source-driver"></a><span data-ttu-id="25f17-102">初始化文本数据源驱动程序</span><span class="sxs-lookup"><span data-stu-id="25f17-102">Initializing the Text Data Source driver</span></span>

<span data-ttu-id="25f17-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="25f17-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="25f17-104">对于文本数据源和 HTML 数据源, 使用相同的数据库驱动程序。</span><span class="sxs-lookup"><span data-stu-id="25f17-104">The same database driver is used for both text data sources and for HTML data sources.</span></span>

<span data-ttu-id="25f17-105">当您安装文本数据源数据库驱动程序时, 安装程序会将一组默认值写入 "引擎" 和 "ISAM Formats" 子项中的 Microsoft Windows 注册表。</span><span class="sxs-lookup"><span data-stu-id="25f17-105">When you install the Text Data Source database driver, the Setup program writes a set of default values to the Microsoft Windows Registry in the Engines and ISAM Formats subkeys.</span></span> <span data-ttu-id="25f17-106">不应直接修改这些设置，而应使用应用程序的安装程序来添加、删除或更改这些设置。</span><span class="sxs-lookup"><span data-stu-id="25f17-106">You should not modify these settings directly; use the setup program for your application to add, remove, or change these settings.</span></span> <span data-ttu-id="25f17-107">以下各节说明了文本数据源数据库驱动程序的初始化和 ISAM 格式设置。</span><span class="sxs-lookup"><span data-stu-id="25f17-107">The following sections describe initialization and ISAM Format settings for the Text Data Source database driver.</span></span>

## <a name="text-data-source-initialization-settings"></a><span data-ttu-id="25f17-108">文本数据源初始化设置</span><span class="sxs-lookup"><span data-stu-id="25f17-108">Text data source initialization settings</span></span>

<span data-ttu-id="25f17-109">**Access Connectivity Engine\\ISAM 格式\\文本文件夹**包括 Acetxt 驱动程序的初始化设置, 用于对文本数据文件的外部访问。</span><span class="sxs-lookup"><span data-stu-id="25f17-109">The **Access Connectivity Engine\\ISAM Formats\\Text folder** includes initialization settings for the Acetxt.dll driver, used for external access to text data files.</span></span> <span data-ttu-id="25f17-110">下面的示例显示了此文件夹中各项的典型设置。</span><span class="sxs-lookup"><span data-stu-id="25f17-110">Typical settings for the entries in this folder are shown in the following example.</span></span>

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

<span data-ttu-id="25f17-111">Microsoft Access 数据库引擎使用如下所示的 Text 文件夹项。</span><span class="sxs-lookup"><span data-stu-id="25f17-111">The Microsoft Access database engine uses the Text folder entries as follows.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="25f17-112">记录</span><span class="sxs-lookup"><span data-stu-id="25f17-112">Entry</span></span></p></th>
<th><p><span data-ttu-id="25f17-113">说明</span><span class="sxs-lookup"><span data-stu-id="25f17-113">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25f17-114">32</span><span class="sxs-lookup"><span data-stu-id="25f17-114">win32</span></span></p></td>
<td><p><span data-ttu-id="25f17-p103">Acetxt.dll 的位置。完整路径在安装时确定。值为 REG_SZ 类型。</span><span class="sxs-lookup"><span data-stu-id="25f17-p103">The location of Acetxt.dll. The full path is determined at the time of installation. Values are of type REG_SZ.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25f17-118">MaxScanRows</span><span class="sxs-lookup"><span data-stu-id="25f17-118">MaxScanRows</span></span></p></td>
<td><p><span data-ttu-id="25f17-p104">推测列类型时要扫描的行数。如果设为 0，则搜索整个文件。默认值为 25。值为 REG_DWORD 类型。</span><span class="sxs-lookup"><span data-stu-id="25f17-p104">The number of rows to be scanned when guessing the column types. If set to 0, the entire file will be searched. The default is 25. Values are of type REG_DWORD.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25f17-123">FirstRowHasNames</span><span class="sxs-lookup"><span data-stu-id="25f17-123">FirstRowHasNames</span></span></p></td>
<td><p><span data-ttu-id="25f17-p105">二进制值，指示表的第一行是否包含列名称。值 01 指示在导入期间从第一行获取列名称。</span><span class="sxs-lookup"><span data-stu-id="25f17-p105">A binary value that indicates whether the first row of the table contains column names. A value of 01 indicates that, during import, column names are taken from the first row.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25f17-126">CharacterSet</span><span class="sxs-lookup"><span data-stu-id="25f17-126">CharacterSet</span></span></p></td>
<td><p><span data-ttu-id="25f17-127">文本页的存储方式指示器。</span><span class="sxs-lookup"><span data-stu-id="25f17-127">An indicator of how text pages are stored.</span></span> <span data-ttu-id="25f17-128">可能的设置包括:</span><span class="sxs-lookup"><span data-stu-id="25f17-128">Possible settings are:</span></span></p>
<p></p>
<ul>
<li><p><span data-ttu-id="25f17-129">ANSI - 计算机的 ANSI 代码页。</span><span class="sxs-lookup"><span data-stu-id="25f17-129">ANSI — The ANSI code page of the machine.</span></span> <span data-ttu-id="25f17-130">AnsiToUnicode 和 UnicodeToAnsi 转换已完成。</span><span class="sxs-lookup"><span data-stu-id="25f17-130">AnsiToUnicode and UnicodeToAnsi conversions done.</span></span></p></li>
<li><p><span data-ttu-id="25f17-131">OEM - 计算机的 OEM 代码页。</span><span class="sxs-lookup"><span data-stu-id="25f17-131">OEM — The OEM code page of the machine.</span></span> <span data-ttu-id="25f17-132">OemToUnicode 和 UnicodeToOem 转换已完成。</span><span class="sxs-lookup"><span data-stu-id="25f17-132">OemToUnicode and UnicodeToOem conversions done.</span></span></p></li>
<li><p><span data-ttu-id="25f17-133">Unicode - 代码页转换未完成。</span><span class="sxs-lookup"><span data-stu-id="25f17-133">Unicode — codepage conversions not done.</span></span></p></li>
<li><p><span data-ttu-id="25f17-134">&lt;十进制数&gt; —特定字符集的代码页编号。</span><span class="sxs-lookup"><span data-stu-id="25f17-134">&lt;decimal number&gt; — The code page number of a specific character set.</span></span> <span data-ttu-id="25f17-135">将要完成与 Unicode 的相互转换。</span><span class="sxs-lookup"><span data-stu-id="25f17-135">Conversions to and from Unicode will be done.</span></span></p></li>
</ul>
<p></p>
<p><span data-ttu-id="25f17-136">默认值为 ANSI。</span><span class="sxs-lookup"><span data-stu-id="25f17-136">The default is ANSI.</span></span> <span data-ttu-id="25f17-137">值为 REG_SZ 类型。</span><span class="sxs-lookup"><span data-stu-id="25f17-137">Values are of type REG_SZ.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25f17-138">Format</span><span class="sxs-lookup"><span data-stu-id="25f17-138">Format</span></span></p></td>
<td><p><span data-ttu-id="25f17-139">可以是以下任何一项: TabDelimited、CSVDelimited、分隔符 (&lt;单字符&gt;)。</span><span class="sxs-lookup"><span data-stu-id="25f17-139">Can be any of the following: TabDelimited, CSVDelimited, Delimited (&lt;single character&gt;).</span></span> <span data-ttu-id="25f17-140">带分隔符的格式的单字符分隔符可以是除双引号 (&quot;) 之外的任何单个字符。</span><span class="sxs-lookup"><span data-stu-id="25f17-140">The single-character delimiter in the Delimited format can be any single character except a double quotation mark (&quot;).</span></span> <span data-ttu-id="25f17-141">默认格式为 CSVDelimited。</span><span class="sxs-lookup"><span data-stu-id="25f17-141">The default is CSVDelimited.</span></span> <span data-ttu-id="25f17-142">值为 REG_SZ 类型。</span><span class="sxs-lookup"><span data-stu-id="25f17-142">Values are of type REG_SZ.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25f17-143">扩展</span><span class="sxs-lookup"><span data-stu-id="25f17-143">Extensions</span></span></p></td>
<td><p><span data-ttu-id="25f17-p112">查找基于文本的数据时将要浏览的任何文件的扩展名。默认值为 txt、csv、tab、asc。值为 REG_SZ 类型。</span><span class="sxs-lookup"><span data-stu-id="25f17-p112">The extension of any files to be browsed when looking for text-based data. The default is txt, csv, tab, asc. Values are of type REG_SZ.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25f17-147">ExportCurrencySymbols</span><span class="sxs-lookup"><span data-stu-id="25f17-147">ExportCurrencySymbols</span></span></p></td>
<td><p><span data-ttu-id="25f17-p113">二进制值，指示导出货币字段时是否包括适当的货币符号。值 01 指示包括该符号，值 00 指示只导出数值数据。默认值为 01。值为 REG_BINARY 类型。</span><span class="sxs-lookup"><span data-stu-id="25f17-p113">A binary value that indicates whether the appropriate currency symbol is included when currency fields are exported. A value of 01 indicates that the symbol is included. A value of 00 indicates that only the numeric data is exported. The default is 01. Values are of type REG_BINARY.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="text-data-source-isam-formats"></a><span data-ttu-id="25f17-153">文本数据源 ISAM 格式</span><span class="sxs-lookup"><span data-stu-id="25f17-153">Text data source ISAM formats</span></span>

<span data-ttu-id="25f17-154">**Access Connectivity Engine\\"ISAM 格式\\" 文本**文件夹包含以下项。</span><span class="sxs-lookup"><span data-stu-id="25f17-154">The **Access Connectivity Engine\\ISAM Formats\\Text** folder contains the following entries.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="25f17-155">项名</span><span class="sxs-lookup"><span data-stu-id="25f17-155">Entry name</span></span></p></th>
<th><p><span data-ttu-id="25f17-156">类型</span><span class="sxs-lookup"><span data-stu-id="25f17-156">Type</span></span></p></th>
<th><p><span data-ttu-id="25f17-157">值</span><span class="sxs-lookup"><span data-stu-id="25f17-157">Value</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25f17-158">Engine</span><span class="sxs-lookup"><span data-stu-id="25f17-158">Engine</span></span></p></td>
<td><p><span data-ttu-id="25f17-159">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="25f17-159">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="25f17-160">文本</span><span class="sxs-lookup"><span data-stu-id="25f17-160">Text</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25f17-161">ExportFilter</span><span class="sxs-lookup"><span data-stu-id="25f17-161">ExportFilter</span></span></p></td>
<td><p><span data-ttu-id="25f17-162">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="25f17-162">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="25f17-163">文本文件（*.txt、*.csv、*.tab、*.asc）</span><span class="sxs-lookup"><span data-stu-id="25f17-163">Text Files (\*.txt; \*.csv; \*.tab; \*.asc)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25f17-164">ImportFilter</span><span class="sxs-lookup"><span data-stu-id="25f17-164">ImportFilter</span></span></p></td>
<td><p><span data-ttu-id="25f17-165">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="25f17-165">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="25f17-166">文本文件（*.txt、*.csv、*.tab、*.asc）</span><span class="sxs-lookup"><span data-stu-id="25f17-166">Text Files (\*.txt; \*.csv; \*.tab; \*.asc)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25f17-167">CanLink</span><span class="sxs-lookup"><span data-stu-id="25f17-167">CanLink</span></span></p></td>
<td><p><span data-ttu-id="25f17-168">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="25f17-168">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="25f17-169">前面</span><span class="sxs-lookup"><span data-stu-id="25f17-169">01</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25f17-170">OneTablePerFile</span><span class="sxs-lookup"><span data-stu-id="25f17-170">OneTablePerFile</span></span></p></td>
<td><p><span data-ttu-id="25f17-171">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="25f17-171">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="25f17-172">前面</span><span class="sxs-lookup"><span data-stu-id="25f17-172">01</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25f17-173">IsamType</span><span class="sxs-lookup"><span data-stu-id="25f17-173">IsamType</span></span></p></td>
<td><p><span data-ttu-id="25f17-174">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="25f17-174">REG_DWORD</span></span></p></td>
<td><p><span data-ttu-id="25f17-175">双面</span><span class="sxs-lookup"><span data-stu-id="25f17-175">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25f17-176">IndexDialog</span><span class="sxs-lookup"><span data-stu-id="25f17-176">IndexDialog</span></span></p></td>
<td><p><span data-ttu-id="25f17-177">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="25f17-177">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="25f17-178">00</span><span class="sxs-lookup"><span data-stu-id="25f17-178">00</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25f17-179">CreateDBOnExport</span><span class="sxs-lookup"><span data-stu-id="25f17-179">CreateDBOnExport</span></span></p></td>
<td><p><span data-ttu-id="25f17-180">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="25f17-180">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="25f17-181">00</span><span class="sxs-lookup"><span data-stu-id="25f17-181">00</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25f17-182">ResultTextImport</span><span class="sxs-lookup"><span data-stu-id="25f17-182">ResultTextImport</span></span></p></td>
<td><p><span data-ttu-id="25f17-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="25f17-183">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="25f17-p114">从外部文件向当前数据库导入数据。更改当前数据库中的数据时不会更改外部文件中的数据。</span><span class="sxs-lookup"><span data-stu-id="25f17-p114">Import data from the external file into the current database. Changing data in the current database will not change data in the external file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25f17-186">ResultTextLink</span><span class="sxs-lookup"><span data-stu-id="25f17-186">ResultTextLink</span></span></p></td>
<td><p><span data-ttu-id="25f17-187">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="25f17-187">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="25f17-p115">在与外部文件链接的当前数据库中创建表。更改当前数据库中的数据将会更改外部文件中的数据。</span><span class="sxs-lookup"><span data-stu-id="25f17-p115">Create a table in the current database that is linked to the external file. Changing data in the current database will change data in the external file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25f17-190">ResultTextExport</span><span class="sxs-lookup"><span data-stu-id="25f17-190">ResultTextExport</span></span></p></td>
<td><p><span data-ttu-id="25f17-191">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="25f17-191">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="25f17-p116">将数据从当前数据库导出到文本文件。如果导出到现有文件，此过程将覆盖数据。</span><span class="sxs-lookup"><span data-stu-id="25f17-p116">Export data from the current database into a text file. This process will overwrite the data if exported to an existing file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25f17-194">SupportsLongNames</span><span class="sxs-lookup"><span data-stu-id="25f17-194">SupportsLongNames</span></span></p></td>
<td><p><span data-ttu-id="25f17-195">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="25f17-195">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="25f17-196">前面</span><span class="sxs-lookup"><span data-stu-id="25f17-196">01</span></span></p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> <span data-ttu-id="25f17-197">[!注释] 更改 Windows 注册表设置后，必须退出并重新启动数据库引擎，以使新的设置生效。</span><span class="sxs-lookup"><span data-stu-id="25f17-197">When you change Windows Registry settings, you must exit and then restart the database engine for the new settings to take effect.</span></span>

## <a name="html-import-isam-formats"></a><span data-ttu-id="25f17-198">HTML 导入 ISAM 格式</span><span class="sxs-lookup"><span data-stu-id="25f17-198">HTML import ISAM formats</span></span>

<span data-ttu-id="25f17-199">**Access Connectivity Engine\\ISAM 格式\\HTML 导入**文件夹包含以下项。</span><span class="sxs-lookup"><span data-stu-id="25f17-199">The **Access Connectivity Engine\\ISAM Formats\\HTML Import** folder contains the following entries.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="25f17-200">项名</span><span class="sxs-lookup"><span data-stu-id="25f17-200">Entry name</span></span></p></th>
<th><p><span data-ttu-id="25f17-201">类型</span><span class="sxs-lookup"><span data-stu-id="25f17-201">Type</span></span></p></th>
<th><p><span data-ttu-id="25f17-202">值</span><span class="sxs-lookup"><span data-stu-id="25f17-202">Value</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25f17-203">Engine</span><span class="sxs-lookup"><span data-stu-id="25f17-203">Engine</span></span></p></td>
<td><p><span data-ttu-id="25f17-204">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="25f17-204">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="25f17-205">文本</span><span class="sxs-lookup"><span data-stu-id="25f17-205">Text</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25f17-206">ImportFilter</span><span class="sxs-lookup"><span data-stu-id="25f17-206">ImportFilter</span></span></p></td>
<td><p><span data-ttu-id="25f17-207">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="25f17-207">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="25f17-208">HTML 文件 (*.ht*)</span><span class="sxs-lookup"><span data-stu-id="25f17-208">HTML Files (*.ht*)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25f17-209">CanLink</span><span class="sxs-lookup"><span data-stu-id="25f17-209">CanLink</span></span></p></td>
<td><p><span data-ttu-id="25f17-210">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="25f17-210">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="25f17-211">前面</span><span class="sxs-lookup"><span data-stu-id="25f17-211">01</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25f17-212">OneTablePerFile</span><span class="sxs-lookup"><span data-stu-id="25f17-212">OneTablePerFile</span></span></p></td>
<td><p><span data-ttu-id="25f17-213">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="25f17-213">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="25f17-214">00</span><span class="sxs-lookup"><span data-stu-id="25f17-214">00</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25f17-215">IsamType</span><span class="sxs-lookup"><span data-stu-id="25f17-215">IsamType</span></span></p></td>
<td><p><span data-ttu-id="25f17-216">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="25f17-216">REG_DWORD</span></span></p></td>
<td><p><span data-ttu-id="25f17-217">双面</span><span class="sxs-lookup"><span data-stu-id="25f17-217">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25f17-218">IndexDialog</span><span class="sxs-lookup"><span data-stu-id="25f17-218">IndexDialog</span></span></p></td>
<td><p><span data-ttu-id="25f17-219">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="25f17-219">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="25f17-220">00</span><span class="sxs-lookup"><span data-stu-id="25f17-220">00</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25f17-221">CreateDBOnExport</span><span class="sxs-lookup"><span data-stu-id="25f17-221">CreateDBOnExport</span></span></p></td>
<td><p><span data-ttu-id="25f17-222">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="25f17-222">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="25f17-223">00</span><span class="sxs-lookup"><span data-stu-id="25f17-223">00</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25f17-224">ResultTextImport</span><span class="sxs-lookup"><span data-stu-id="25f17-224">ResultTextImport</span></span></p></td>
<td><p><span data-ttu-id="25f17-225">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="25f17-225">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="25f17-p117">从外部文件向当前数据库导入数据。更改当前数据库中的数据时不会更改外部文件中的数据。</span><span class="sxs-lookup"><span data-stu-id="25f17-p117">Import data from the external file into the current database. Changing data in the current database will not change data in the external file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25f17-228">ResultTextLink</span><span class="sxs-lookup"><span data-stu-id="25f17-228">ResultTextLink</span></span></p></td>
<td><p><span data-ttu-id="25f17-229">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="25f17-229">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="25f17-p118">在与外部文件链接的当前数据库中创建表。更改当前数据库中的数据将会更改外部文件中的数据。</span><span class="sxs-lookup"><span data-stu-id="25f17-p118">Create a table in the current database that is linked to the external file. Changing data in the current database will change data in the external file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25f17-232">SupportsLongNames</span><span class="sxs-lookup"><span data-stu-id="25f17-232">SupportsLongNames</span></span></p></td>
<td><p><span data-ttu-id="25f17-233">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="25f17-233">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="25f17-234">前面</span><span class="sxs-lookup"><span data-stu-id="25f17-234">01</span></span></p></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="25f17-235">[!注释] 更改 Windows 注册表设置后，必须退出并重新启动数据库引擎，以使新的设置生效。</span><span class="sxs-lookup"><span data-stu-id="25f17-235">When you change Windows Registry settings, you must exit and then restart the database engine for the new settings to take effect.</span></span>

## <a name="html-export-isam-formats"></a><span data-ttu-id="25f17-236">HTML 导出 ISAM 格式</span><span class="sxs-lookup"><span data-stu-id="25f17-236">HTML export ISAM formats</span></span>

<span data-ttu-id="25f17-237">**Access Connectivity Engine\\ISAM 格式\\HTML 导出**文件夹包含以下项。</span><span class="sxs-lookup"><span data-stu-id="25f17-237">The **Access Connectivity Engine\\ISAM Formats\\HTML Export** folder contains the following entries.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="25f17-238">项名</span><span class="sxs-lookup"><span data-stu-id="25f17-238">Entry name</span></span></p></th>
<th><p><span data-ttu-id="25f17-239">类型</span><span class="sxs-lookup"><span data-stu-id="25f17-239">Type</span></span></p></th>
<th><p><span data-ttu-id="25f17-240">值</span><span class="sxs-lookup"><span data-stu-id="25f17-240">Value</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25f17-241">Engine</span><span class="sxs-lookup"><span data-stu-id="25f17-241">Engine</span></span></p></td>
<td><p><span data-ttu-id="25f17-242">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="25f17-242">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="25f17-243">文本</span><span class="sxs-lookup"><span data-stu-id="25f17-243">Text</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25f17-244">ExportFilter</span><span class="sxs-lookup"><span data-stu-id="25f17-244">ExportFilter</span></span></p></td>
<td><p><span data-ttu-id="25f17-245">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="25f17-245">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="25f17-246">HTML 文件 (\*.htm)</span><span class="sxs-lookup"><span data-stu-id="25f17-246">HTML Files (\*.htm)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25f17-247">CanLink</span><span class="sxs-lookup"><span data-stu-id="25f17-247">CanLink</span></span></p></td>
<td><p><span data-ttu-id="25f17-248">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="25f17-248">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="25f17-249">00</span><span class="sxs-lookup"><span data-stu-id="25f17-249">00</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25f17-250">OneTablePerFile</span><span class="sxs-lookup"><span data-stu-id="25f17-250">OneTablePerFile</span></span></p></td>
<td><p><span data-ttu-id="25f17-251">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="25f17-251">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="25f17-252">前面</span><span class="sxs-lookup"><span data-stu-id="25f17-252">01</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25f17-253">IsamType</span><span class="sxs-lookup"><span data-stu-id="25f17-253">IsamType</span></span></p></td>
<td><p><span data-ttu-id="25f17-254">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="25f17-254">REG_DWORD</span></span></p></td>
<td><p><span data-ttu-id="25f17-255">双面</span><span class="sxs-lookup"><span data-stu-id="25f17-255">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25f17-256">IndexDialog</span><span class="sxs-lookup"><span data-stu-id="25f17-256">IndexDialog</span></span></p></td>
<td><p><span data-ttu-id="25f17-257">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="25f17-257">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="25f17-258">00</span><span class="sxs-lookup"><span data-stu-id="25f17-258">00</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25f17-259">CreateDBOnExport</span><span class="sxs-lookup"><span data-stu-id="25f17-259">CreateDBOnExport</span></span></p></td>
<td><p><span data-ttu-id="25f17-260">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="25f17-260">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="25f17-261">00</span><span class="sxs-lookup"><span data-stu-id="25f17-261">00</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25f17-262">ResultTextExport</span><span class="sxs-lookup"><span data-stu-id="25f17-262">ResultTextExport</span></span></p></td>
<td><p><span data-ttu-id="25f17-263">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="25f17-263">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="25f17-p119">将数据从当前数据库导出到文本文件。如果导出到现有文件，此过程将覆盖数据。</span><span class="sxs-lookup"><span data-stu-id="25f17-p119">Export data from the current database into a text file. This process will overwrite the data if exported to an existing file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25f17-266">SupportsLongNames</span><span class="sxs-lookup"><span data-stu-id="25f17-266">SupportsLongNames</span></span></p></td>
<td><p><span data-ttu-id="25f17-267">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="25f17-267">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="25f17-268">前面</span><span class="sxs-lookup"><span data-stu-id="25f17-268">01</span></span></p></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="25f17-269">[!注释] 更改 Windows 注册表设置后，必须退出并重新启动数据库引擎，以使新的设置生效。</span><span class="sxs-lookup"><span data-stu-id="25f17-269">When you change Windows Registry settings, you must exit and then restart the database engine for the new settings to take effect.</span></span>

## <a name="customizing-the-schemaini-file-for-text-and-html-data"></a><span data-ttu-id="25f17-270">自定义文本和 HTML 数据的 schema.ini 文件</span><span class="sxs-lookup"><span data-stu-id="25f17-270">Customizing the Schema.ini file for text and HTML data</span></span>

<span data-ttu-id="25f17-p120">若要读取、导入或导出文本和 HTML 数据，除要在 .ini 文件中包括文本 ISAM 信息外，还需要创建 Schema.ini 文件。Schema.ini 包含数据源的结构信息：如何设置文本文件的格式、如果在导入时读取文本文件、文件的默认导出格式是什么。下面的示例显示了定宽文件 Filename.txt 的布局：</span><span class="sxs-lookup"><span data-stu-id="25f17-p120">To read, import, or export text and HTML data, you need to create a Schema.ini file in addition to including the Text ISAM information in the .ini file. Schema.ini contains the specifics of a data source: how the text file is formatted, how it is read at import time, and what the default export format is for files. The following examples show the layout for a fixed-width file, Filename.txt:</span></span>

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

<span data-ttu-id="25f17-274">类似地，分隔文件的格式按如下所示进行指定：</span><span class="sxs-lookup"><span data-stu-id="25f17-274">Similarly, the format for a delimited file is specified as follows:</span></span>

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

<span data-ttu-id="25f17-275">如果要将数据导出到分隔文本文件中，还要指定该文件的格式：</span><span class="sxs-lookup"><span data-stu-id="25f17-275">If you are exporting data into a delimited text file, specify the format for that file as well:</span></span>

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

<span data-ttu-id="25f17-p121">"My Special Export"示例引用了特定导出选项。可以在连接时指定任何不同的导出选项。最后一个示例还对应于在连接时可选要传递的数据源名称 (DSN)。所有这三个格式部分都可以包括在同一个 .ini 文件中。</span><span class="sxs-lookup"><span data-stu-id="25f17-p121">The My Special Export example refers to a specific export option; you can specify any variation of export options at connect time. This last example also corresponds to a data source name (DSN) that can be optionally passed at connect time. All three format sections can be included in the same .ini file.</span></span>

<span data-ttu-id="25f17-279">Microsoft Access 数据库引擎使用如下所示的 Schema.ini 项。</span><span class="sxs-lookup"><span data-stu-id="25f17-279">The Microsoft Access database engine uses the Schema.ini entries as follows.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="25f17-280">记录</span><span class="sxs-lookup"><span data-stu-id="25f17-280">Entry</span></span></p></th>
<th><p><span data-ttu-id="25f17-281">说明</span><span class="sxs-lookup"><span data-stu-id="25f17-281">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25f17-282">ColNameHeader</span><span class="sxs-lookup"><span data-stu-id="25f17-282">ColNameHeader</span></span></p></td>
<td><p><span data-ttu-id="25f17-283">可设为 <strong>True</strong>（指示由第一条数据记录指定列的名称）或 <strong>False</strong>。</span><span class="sxs-lookup"><span data-stu-id="25f17-283">Can be set to either <strong>True</strong> (indicating that the first record of data specifies the column names) or <strong>False</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25f17-284">Format</span><span class="sxs-lookup"><span data-stu-id="25f17-284">Format</span></span></p></td>
<td><p><span data-ttu-id="25f17-285">可设置为以下值之一: TabDelimited、CSVDelimited、分隔字符 (&lt;单字符&gt;) 或 FixedLength。</span><span class="sxs-lookup"><span data-stu-id="25f17-285">Can be set to one of the following values: TabDelimited, CSVDelimited, Delimited (&lt;single character&gt;), or FixedLength.</span></span> <span data-ttu-id="25f17-286">为分隔文件格式指定的分隔符可以是除双引号 (&quot;) 之外的任何单个字符。</span><span class="sxs-lookup"><span data-stu-id="25f17-286">The delimiter specified for the Delimited file format can be any single character except a double quotation mark (&quot;).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25f17-287">FixedFormat</span><span class="sxs-lookup"><span data-stu-id="25f17-287">FixedFormat</span></span></p></td>
<td><p><span data-ttu-id="25f17-288">仅在 Format 为 FixedLength 时使用，此项可以设为下列值之一：RaggedEdge 或 TrueFixedLength。</span><span class="sxs-lookup"><span data-stu-id="25f17-288">Only used when the Format is FixedLength, this can be set to one of the following values: RaggedEdge or TrueFixedLength.</span></span> <span data-ttu-id="25f17-289">RaggedEdge 允许行以回车符终止。</span><span class="sxs-lookup"><span data-stu-id="25f17-289">RaggedEdge allows rows to be terminated with a Carriage Return character.</span></span> <span data-ttu-id="25f17-290">TrueFixedLength 要求每一行都是确切的字符数，并且假定不在行边界的任何回车符都嵌入在字段中。</span><span class="sxs-lookup"><span data-stu-id="25f17-290">TrueFixedLength requires each row to be an exact number of characters, and any Carriage Return characters not at a row boundary are assumed to be embedded in a field.</span></span> <span data-ttu-id="25f17-291">如果没有此设置，默认值为 RaggedEdge。</span><span class="sxs-lookup"><span data-stu-id="25f17-291">If this setting is not present, the default value is RaggedEdge.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25f17-292">MaxScanRows</span><span class="sxs-lookup"><span data-stu-id="25f17-292">MaxScanRows</span></span></p></td>
<td><p><span data-ttu-id="25f17-p124">指示在推测列数据类型时要扫描的行数。如果设为 0，则搜索整个文件。</span><span class="sxs-lookup"><span data-stu-id="25f17-p124">Indicates the number of rows to be scanned when guessing the column data types. If this is set to 0, the entire file is searched.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25f17-295">CharacterSet</span><span class="sxs-lookup"><span data-stu-id="25f17-295">CharacterSet</span></span></p></td>
<td><p><span data-ttu-id="25f17-296">可设为 OEM、ANSI、UNICODE 或有效代码页的十进制数，指示源文件的字符集。</span><span class="sxs-lookup"><span data-stu-id="25f17-296">Can be set to OEM, ANSI, UNICODE, or the decimal number of a valid code page, and indicates the character set of the source file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25f17-297">DateTimeFormat</span><span class="sxs-lookup"><span data-stu-id="25f17-297">DateTimeFormat</span></span></p></td>
<td><p><span data-ttu-id="25f17-p125">可设为指示日期和时间的格式字符串。如果导入/导出时的所有日期/时间字段均用相同格式处理，则应指定此项。除 AM 和 PM 以外，所有 Microsoft Jet 数据库引擎格式均受支持。如果没有格式字符串，则使用 Windows“控制面板”的短日期图片和时间选项。</span><span class="sxs-lookup"><span data-stu-id="25f17-p125">Can be set to a format string indicating dates and times. This entry should be specified if all date/time fields in the import/export are handled with the same format. All of the Microsoft Jet database engine formats except AM and PM are supported. In the absence of a format string, the Windows Control Panel short date picture and time options are used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25f17-302">CurrencySymbol</span><span class="sxs-lookup"><span data-stu-id="25f17-302">CurrencySymbol</span></span></p></td>
<td><p><span data-ttu-id="25f17-p126">指示文本文件中的货币值要使用的货币符号。例如，美元符号 ($) 和德国马克。如果没有此项，则使用 Windows 控制面板中的默认值。</span><span class="sxs-lookup"><span data-stu-id="25f17-p126">Indicates the currency symbol to be used for currency values in the text file. Examples include the dollar sign ($) and Dm. If this entry is absent, the default value in the Windows Control Panel is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25f17-306">CurrencyPosFormat</span><span class="sxs-lookup"><span data-stu-id="25f17-306">CurrencyPosFormat</span></span></p></td>
<td><p><span data-ttu-id="25f17-307">可以设置为以下任意值: 不带分隔的货币符号前缀 ($1) 不带分隔符的货币符号后缀 ($1) 使用一个字符分隔的货币符号前缀 ($1) 使用一个字符分隔的货币符号后缀 ($1) 如果此项不存在, 则使用 Windows 控制面板中的默认值。</span><span class="sxs-lookup"><span data-stu-id="25f17-307">Can be set to any of the following values: Currency symbol prefix with no separation ($1) Currency symbol suffix with no separation (1$) Currency symbol prefix with one character separation ($ 1) Currency symbol suffix with one character separation (1 $) If this entry is absent, the default value in the Windows Control Panel is used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25f17-308">CurrencyDigits</span><span class="sxs-lookup"><span data-stu-id="25f17-308">CurrencyDigits</span></span></p></td>
<td><p><span data-ttu-id="25f17-p127">指定货币数额的小数部分使用的数字位数。如果没有此项，则使用 Windows 控制面板中的默认值。</span><span class="sxs-lookup"><span data-stu-id="25f17-p127">Specifies the number of digits used for the fractional part of a currency amount. If this entry is absent, the default value in the Windows Control Panel is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25f17-311">CurrencyNegFormat</span><span class="sxs-lookup"><span data-stu-id="25f17-311">CurrencyNegFormat</span></span></p></td>
<td><p><span data-ttu-id="25f17-312">可以是下列值之一: ($1) – $1 $ – $1 1 – ($1) – $1 1 – $1 [– $1 – $1 $1 – $1 – $ – 1 1 – $ ($1) ($1) 美元符号显示在此示例的用途中, 但应将其替换为实际程序中相应的 CurrencySymbol 值。</span><span class="sxs-lookup"><span data-stu-id="25f17-312">Can be one of the following values: ($1) –$1 $–1 $1– (1$) –1$ 1–$ 1$– –1 $ –$ 1 1 $– $ 1– $ –1 1– $ ($ 1) (1 $) The dollar sign is shown for purposes of this example, but it should be replaced with the appropriate CurrencySymbol value in the actual program.</span></span> <span data-ttu-id="25f17-313">如果没有此项，则使用 Windows 控制面板中的默认值。</span><span class="sxs-lookup"><span data-stu-id="25f17-313">If this entry is absent, the default value in the Windows Control Panel is used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25f17-314">CurrencyThousandSymbol</span><span class="sxs-lookup"><span data-stu-id="25f17-314">CurrencyThousandSymbol</span></span></p></td>
<td><p><span data-ttu-id="25f17-p129">指示用于在文本文件中按千分隔货币值的单字符符号。如果没有此项，则使用 Windows 控制面板中的默认值。</span><span class="sxs-lookup"><span data-stu-id="25f17-p129">Indicates the single-character symbol to be used for separating currency values by thousands in the text file. If this entry is absent, the default value in the Windows Control Panel is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25f17-317">CurrencyDecimalSymbol</span><span class="sxs-lookup"><span data-stu-id="25f17-317">CurrencyDecimalSymbol</span></span></p></td>
<td><p><span data-ttu-id="25f17-p130">可设为用于分隔货币数额的整数部分和小数部分的任何单字符。如果没有此项，则使用 Windows 控制面板中的默认值。</span><span class="sxs-lookup"><span data-stu-id="25f17-p130">Can be set to any single character that is used to separate the whole from the fractional part of a currency amount. If this entry is absent, the default value in the Windows Control Panel is used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25f17-320">DecimalSymbol</span><span class="sxs-lookup"><span data-stu-id="25f17-320">DecimalSymbol</span></span></p></td>
<td><p><span data-ttu-id="25f17-p131">可设为用于分隔数字的整数部分和小数部分的任何单字符。如果没有此项，则使用 Windows 控制面板中的默认值。</span><span class="sxs-lookup"><span data-stu-id="25f17-p131">Can be set to any single character that is used to separate the integer from the fractional part of a number. If this entry is absent, the default value in the Windows Control Panel is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25f17-323">NumberDigits</span><span class="sxs-lookup"><span data-stu-id="25f17-323">NumberDigits</span></span></p></td>
<td><p><span data-ttu-id="25f17-p132">指示数字的小数部分的小数位数。如果没有此项，则使用 Windows 控制面板中的默认值。</span><span class="sxs-lookup"><span data-stu-id="25f17-p132">Indicates the number of decimal digits in the fractional portion of a number. If this entry is absent, the default value in the Windows Control Panel is used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25f17-326">NumberLeadingZeros</span><span class="sxs-lookup"><span data-stu-id="25f17-326">NumberLeadingZeros</span></span></p></td>
<td><p><span data-ttu-id="25f17-327">指定大于 -1 但小于 1 的小数值是否应包含几个前导零。该值可以为 False（没有前导零）或 True。</span><span class="sxs-lookup"><span data-stu-id="25f17-327">Specifies whether a decimal value less than 1 and greater than –1 should contain leading zeros; this value can either be False (no leading zeros) or True.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25f17-328">Col1、Col2、.。。</span><span class="sxs-lookup"><span data-stu-id="25f17-328">Col1, Col2, …</span></span></p></td>
<td><p><span data-ttu-id="25f17-329">列出要读取的文本文件中的列。</span><span class="sxs-lookup"><span data-stu-id="25f17-329">Lists the columns in the text file to be read.</span></span> <span data-ttu-id="25f17-330">此条目的格式应为: <em>Coln</em>=<em>columnName</em>类型 [Width <em> #</em>] <em>columnname</em>: 使用嵌入空格的列名称应括在引号中。</span><span class="sxs-lookup"><span data-stu-id="25f17-330">The format of this entry should be: <em>Coln</em>=<em>columnName</em> type [Width <em>#</em>] <em>columnName</em>: Column names with embedded spaces should be enclosed in quotation marks.</span></span> <span data-ttu-id="25f17-331"><em>类型</em>: 可以是位、字节、短、长、十进制、Currency、Single、Double、DateTime。</span><span class="sxs-lookup"><span data-stu-id="25f17-331"><em>type</em>: Can be Bit, Byte, Short, Long, Decimal, Currency, Single, Double, DateTime.</span></span> <span data-ttu-id="25f17-332">二进制、OLE、文本或备注。</span><span class="sxs-lookup"><span data-stu-id="25f17-332">Binary, OLE, Text, or Memo.</span></span> <span data-ttu-id="25f17-333">此外, 还支持以下 ODBC 文本驱动程序类型: Char (与文本相同) 浮点 (与双精度型相同) LongChar (与备注相同) 日期<em>日期格式</em>在备注类型中, "其他格式标记 [属性 Hyperlink]" 可以是用于指定在 Microsoft Access 中应为活动 url 的列。</span><span class="sxs-lookup"><span data-stu-id="25f17-333">In addition, the following ODBC Text Driver types are supported: Char (same as Text) Float (same as Double) Integer (same as Short) LongChar (same as Memo) Date <em>date format</em> In the case of a Memo type an additional format marker [Attribute Hyperlink] can be used to specify columns that should be active URLs in Microsoft Access.</span></span> <span data-ttu-id="25f17-334">在 Decimal 类型的情况下，应使用附加格式标记 [Scale #] Precision #]。</span><span class="sxs-lookup"><span data-stu-id="25f17-334">In the case of a Decimal type the additional format markers [Scale #] Precision #] should be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25f17-335">TextDelimiter</span><span class="sxs-lookup"><span data-stu-id="25f17-335">TextDelimiter</span></span></p></td>
<td><p><span data-ttu-id="25f17-336">可设为用于对包含任何其他特殊字符的字符串进行分隔的任何单字符。</span><span class="sxs-lookup"><span data-stu-id="25f17-336">Can be set to any single character that is used to delimit strings that contain any of the other special characters.</span></span> <span data-ttu-id="25f17-337">例如，</span><span class="sxs-lookup"><span data-stu-id="25f17-337">E.g.</span></span> <span data-ttu-id="25f17-338">&quot;abc&quot;、&quot;xyz、pqr&quot;、&quot;hij&quot;如果此条目不存在, 则默认分隔符是一个双引号。</span><span class="sxs-lookup"><span data-stu-id="25f17-338">&quot;abc&quot;,&quot;xyz,pqr&quot;,&quot;hij&quot; If this entry is not present the default delimiter is a double quote.</span></span> <span data-ttu-id="25f17-339">如果此项是字符串&quot;none&quot; , 则不会将任何字符视为分隔符。</span><span class="sxs-lookup"><span data-stu-id="25f17-339">If this entry is the string &quot;none&quot; then no characters will be treated as delimiters.</span></span></p></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="25f17-340">[!注释] 更改 Schema.ini 文件设置时，必须先退出数据库引擎，然后再重新启动它，这样，新设置才会生效。</span><span class="sxs-lookup"><span data-stu-id="25f17-340">When you change Schema.ini file settings, you must exit and then restart the database engine for the new settings to take effect.</span></span>


