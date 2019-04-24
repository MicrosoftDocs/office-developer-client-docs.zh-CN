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
ms.openlocfilehash: c3424fd4b85108120ea4accc2dfa65d55394f0d2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291433"
---
# <a name="initializing-the-microsoft-excel-driver"></a><span data-ttu-id="99431-102">初始化 Microsoft Excel 驱动程序</span><span class="sxs-lookup"><span data-stu-id="99431-102">Initializing the Microsoft Excel driver</span></span>

<span data-ttu-id="99431-103">**适用**于: Excel 2016 |Access 2016 |Access 2013 |Office 2013 |Excel 2013 |Office for business Access 2013 |Excel 2010 |Access 2010</span><span class="sxs-lookup"><span data-stu-id="99431-103">**Applies to**: Excel 2016 | Access 2016 | Access 2013 | Office 2013 | Excel 2013 | Office for business Access 2013 | Excel 2010 | Access 2010</span></span>

<span data-ttu-id="99431-104">安装 Excel 驱动程序时, 安装程序会将一组默认值写入 "引擎" 和 "ISAM Formats" 子项中的 Windows 注册表中。</span><span class="sxs-lookup"><span data-stu-id="99431-104">When you install the Excel driver, the Setup program writes a set of default values to the Windows Registry in the Engines and ISAM Formats subkeys.</span></span> <span data-ttu-id="99431-105">不应直接修改这些设置，而应使用应用程序的安装程序来添加、删除或更改这些设置。</span><span class="sxs-lookup"><span data-stu-id="99431-105">You should not modify these settings directly; use the setup program for your application to add, remove, or change these settings.</span></span> <span data-ttu-id="99431-106">以下各节说明了 Microsoft Excel 数据库驱动程序的初始化和 ISAM 格式设置。</span><span class="sxs-lookup"><span data-stu-id="99431-106">The following sections describe initialization and ISAM Format settings for the Microsoft Excel database driver.</span></span>

## <a name="excel-initialization-settings"></a><span data-ttu-id="99431-107">Excel 初始化设置</span><span class="sxs-lookup"><span data-stu-id="99431-107">Excel initialization settings</span></span>

<span data-ttu-id="99431-108">**Access Connectivity Engine Engine\\\\Excel**文件夹包括用于对 Microsoft Excel 工作表进行外部访问的 Aceexcl 驱动程序的初始化设置。</span><span class="sxs-lookup"><span data-stu-id="99431-108">The **Access Connectivity Engine\\Engines\\Excel** folder includes initialization settings for the Aceexcl.dll driver, used for external access to Microsoft Excel worksheets.</span></span> <span data-ttu-id="99431-109">下面的示例显示了此文件夹中各项的典型设置。</span><span class="sxs-lookup"><span data-stu-id="99431-109">Typical settings for the entries in this folder are shown in the following example.</span></span>

```vb
    win32=<path>\ Aceexcl.dll  
    
    TypeGuessRows=8 
    
    ImportMixedTypes=Text 
    
    AppendBlankRows=1 
    
    FirstRowHasNames=Yes
```

<span data-ttu-id="99431-110">Microsoft Access 数据库引擎使用如下所示的 Excel 文件夹项。</span><span class="sxs-lookup"><span data-stu-id="99431-110">The Microsoft Access database engine uses the Excel folder entries as follows.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="99431-111">记录</span><span class="sxs-lookup"><span data-stu-id="99431-111">Entry</span></span></p></th>
<th><p><span data-ttu-id="99431-112">说明</span><span class="sxs-lookup"><span data-stu-id="99431-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99431-113">32</span><span class="sxs-lookup"><span data-stu-id="99431-113">win32</span></span></p></td>
<td><p><span data-ttu-id="99431-p103">msexcl40.dll 的位置。完整路径在安装时确定。值为 REG_SZ 类型。</span><span class="sxs-lookup"><span data-stu-id="99431-p103">The location of msexcl40.dll. The full path is determined at the time of installation. Values are of type REG_SZ.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99431-117">TypeGuessRows</span><span class="sxs-lookup"><span data-stu-id="99431-117">TypeGuessRows</span></span></p></td>
<td><p><span data-ttu-id="99431-p104">确定数据类型时需要检查的行数。数据类型根据找到的数据种类的最大数目确定。如果这样做无效，则按如下顺序确定数据类型：数字、货币、日期、文本、布尔。如果遇到的数据与所猜测的列数据类型不匹配，该数据将作为 <strong>Null</strong> 值返回。在导入时，如果某列使用混合数据类型，则整个列将根据 ImportMixedTypes 设置转换数据类型。 需要检查的默认行数为 8 行。值的类型为 REG_DWORD。  </span><span class="sxs-lookup"><span data-stu-id="99431-p104">The number of rows to be checked for the data type. The data type is determined given the maximum number of kinds of data found. If there is a tie, the data type is determined in the following order: Number, Currency, Date, Text, Boolean. If data is encountered that does not match the data type guessed for the column, it is returned as a <strong>Null</strong> value. On import, if a column has mixed data types, the entire column will be cast according to the ImportMixedTypes setting. The default number of rows to be checked is 8. Values are of type REG_DWORD.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99431-125">ImportMixedTypes</span><span class="sxs-lookup"><span data-stu-id="99431-125">ImportMixedTypes</span></span></p></td>
<td><p><span data-ttu-id="99431-p105">可设为"MajorityType"或"Text"。如果设为"MajorityType"，混合数据类型的列在导入时将强制转换为占优势地位的数据类型。如果设为"Text"，混合数据类型的列在导入时将强制转换为"Text"。默认设置是"Text"。值为 REG_SZ 类型。</span><span class="sxs-lookup"><span data-stu-id="99431-p105">Can be set to MajorityType or Text. If set to MajorityType, columns of mixed data types will be cast to the predominate data type on import. If set to Text, columns of mixed data types will be cast to Text on import. The default is Text. Values are of type REG_SZ.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99431-131">AppendBlankRows</span><span class="sxs-lookup"><span data-stu-id="99431-131">AppendBlankRows</span></span></p></td>
<td><p><span data-ttu-id="99431-p106">在添加新数据前，将追加到 3.5 版或 4.0 版工作表末尾的空白行数。例如，如果 AppendBlankRows 设为 4，Microsoft Jet 将在向工作表追加包含数据的行之前先追加 4 个空白行。此设置的整数值范围可以从 0 到 16。默认值为 01（追加一个附加行）。值为 REG_DWORD 类型。</span><span class="sxs-lookup"><span data-stu-id="99431-p106">The number of blank rows to be appended to the end of a Version 3.5 or Version 4.0 worksheet before new data is added. For example, if AppendBlankRows is set to 4, Microsoft Jet will append 4 blank rows to the end of the worksheet before appending rows that contain data. Integer values for this setting can range from 0 to 16; the default is 01 (one additional row appended). Values are of type REG_DWORD.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99431-136">FirstRowHasNames</span><span class="sxs-lookup"><span data-stu-id="99431-136">FirstRowHasNames</span></span></p></td>
<td><p><span data-ttu-id="99431-p107">指示表的第一行是否包含列名称的二进制值。值 01 指示在导入期间从第一行获取列名称。值 00 指示第一行中没有列名称。列名称显示为 F1、F2、F3 等。默认值为 01。值为 REG_BINARY 类型。</span><span class="sxs-lookup"><span data-stu-id="99431-p107">A binary value that indicates whether the first row of the table contains column names. A value of 01 indicates that, during import, column names are taken from the first row. A value of 00 indicates no column names in the first row; column names appear as F1, F2, F3, and so on. The default is 01. Values are of type REG_BINARY.</span></span></p></td>
</tr>
</tbody>
</table>

<br/>

<span data-ttu-id="99431-142">**Access Connectivity Engine\\引擎\\Excel 8.0**文件夹包含以下项, 这些项适用于 Microsoft Excel 97。</span><span class="sxs-lookup"><span data-stu-id="99431-142">The **Access Connectivity Engine\\Engines\\Excel 8.0** folder contains the following entries, which apply to Microsoft Excel 97.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="99431-143">项名</span><span class="sxs-lookup"><span data-stu-id="99431-143">Entry name</span></span></p></th>
<th><p><span data-ttu-id="99431-144">类型</span><span class="sxs-lookup"><span data-stu-id="99431-144">Type</span></span></p></th>
<th><p><span data-ttu-id="99431-145">值</span><span class="sxs-lookup"><span data-stu-id="99431-145">Value</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99431-146">Engine</span><span class="sxs-lookup"><span data-stu-id="99431-146">Engine</span></span></p></td>
<td><p><span data-ttu-id="99431-147">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="99431-147">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="99431-148">Excel</span><span class="sxs-lookup"><span data-stu-id="99431-148">Excel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99431-149">ExportFilter</span><span class="sxs-lookup"><span data-stu-id="99431-149">ExportFilter</span></span></p></td>
<td><p><span data-ttu-id="99431-150">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="99431-150">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="99431-151">Microsoft Excel 97-2000 (\*.xls)</span><span class="sxs-lookup"><span data-stu-id="99431-151">Microsoft Excel 97-2000 (\*.xls)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99431-152">CanLink</span><span class="sxs-lookup"><span data-stu-id="99431-152">CanLink</span></span></p></td>
<td><p><span data-ttu-id="99431-153">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="99431-153">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="99431-154">前面</span><span class="sxs-lookup"><span data-stu-id="99431-154">01</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99431-155">OneTablePerFile</span><span class="sxs-lookup"><span data-stu-id="99431-155">OneTablePerFile</span></span></p></td>
<td><p><span data-ttu-id="99431-156">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="99431-156">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="99431-157">00</span><span class="sxs-lookup"><span data-stu-id="99431-157">00</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99431-158">IsamType</span><span class="sxs-lookup"><span data-stu-id="99431-158">IsamType</span></span></p></td>
<td><p><span data-ttu-id="99431-159">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="99431-159">REG_DWORD</span></span></p></td>
<td><p><span data-ttu-id="99431-160">1</span><span class="sxs-lookup"><span data-stu-id="99431-160">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99431-161">IndexDialog</span><span class="sxs-lookup"><span data-stu-id="99431-161">IndexDialog</span></span></p></td>
<td><p><span data-ttu-id="99431-162">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="99431-162">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="99431-163">00</span><span class="sxs-lookup"><span data-stu-id="99431-163">00</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99431-164">CreateDBOnExport</span><span class="sxs-lookup"><span data-stu-id="99431-164">CreateDBOnExport</span></span></p></td>
<td><p><span data-ttu-id="99431-165">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="99431-165">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="99431-166">前面</span><span class="sxs-lookup"><span data-stu-id="99431-166">01</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99431-167">ResultTextExport</span><span class="sxs-lookup"><span data-stu-id="99431-167">ResultTextExport</span></span></p></td>
<td><p><span data-ttu-id="99431-168">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="99431-168">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="99431-p108">将数据从当前数据库导出到 Microsoft Excel 97 文件。如果导出到现有文件，此过程将覆盖数据。</span><span class="sxs-lookup"><span data-stu-id="99431-p108">Export data from the current database into a Microsoft Excel 97 file. This process will overwrite the data if exported to an existing file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99431-171">SupportsLongNames</span><span class="sxs-lookup"><span data-stu-id="99431-171">SupportsLongNames</span></span></p></td>
<td><p><span data-ttu-id="99431-172">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="99431-172">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="99431-173">前面</span><span class="sxs-lookup"><span data-stu-id="99431-173">01</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="using-the-typeguessrows-setting-for-excel-driver"></a><span data-ttu-id="99431-174">使用 Excel 驱动程序的 TypeGuessRows 设置</span><span class="sxs-lookup"><span data-stu-id="99431-174">Using the TypeGuessRows setting for Excel Driver</span></span>
<span data-ttu-id="99431-175">使用 Microsoft Excel 驱动程序时, 可以使用**TypeGuessRows**注册表值来配置要检查的数据类型的行数。</span><span class="sxs-lookup"><span data-stu-id="99431-175">When you use Microsoft Excel Driver, you can use the **TypeGuessRows** registry value to configure how many rows are to be checked for the data type.</span></span> <span data-ttu-id="99431-176">**TypeGuessRows**值位于以下注册表子项下:</span><span class="sxs-lookup"><span data-stu-id="99431-176">The **TypeGuessRows** value is located under the following registry subkey:</span></span>

# <a name="office-2016taboffice-2016"></a>[<span data-ttu-id="99431-177">Office 2016</span><span class="sxs-lookup"><span data-stu-id="99431-177">Office 2016</span></span>](#tab/office-2016)

<span data-ttu-id="99431-178">对于 MSI 安装的 Office</span><span class="sxs-lookup"><span data-stu-id="99431-178">For an MSI installation of Office</span></span>

- <span data-ttu-id="99431-179">对于在 64 windows 上的32位或64位的 office 上为32位的 office, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="99431-179">For 32-bit Office on 32-bit Windows or 64-bit Office on 64-bit Windows:</span></span>
    
  <span data-ttu-id="99431-180">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\16.0\Access 连接 Engine\Engines\Excel**</span><span class="sxs-lookup"><span data-stu-id="99431-180">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\16.0\Access Connectivity Engine\Engines\Excel**</span></span>

- <span data-ttu-id="99431-181">对于64位 Windows 上的32位 Office:</span><span class="sxs-lookup"><span data-stu-id="99431-181">For 32-bit Office on 64-bit Windows:</span></span>

  <span data-ttu-id="99431-182">**HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Office\16.0\Access 连接 Engine\Engines\Excel**</span><span class="sxs-lookup"><span data-stu-id="99431-182">**HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Office\16.0\Access Connectivity Engine\Engines\Excel**</span></span>
    
<span data-ttu-id="99431-183">对于 Office 即点即用安装</span><span class="sxs-lookup"><span data-stu-id="99431-183">For a Click-to-Run installation of Office</span></span>

- <span data-ttu-id="99431-184">对于在 64 windows 上的32位或64位的 office 上为32位的 office, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="99431-184">For 32-bit Office on 32-bit Windows or 64-bit Office on 64-bit Windows:</span></span>
    
  <span data-ttu-id="99431-185">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\ClickToRun\REGISTRY\MACHINE\Software\Microsoft\Office\16.0\Access 连接 Engine\Engines\Excel**</span><span class="sxs-lookup"><span data-stu-id="99431-185">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\ClickToRun\REGISTRY\MACHINE\Software\Microsoft\Office\16.0\Access Connectivity Engine\Engines\Excel**</span></span>

- <span data-ttu-id="99431-186">对于64位 Windows 上的32位 Office:</span><span class="sxs-lookup"><span data-stu-id="99431-186">For 32-bit Office on 64-bit Windows:</span></span>
    
  <span data-ttu-id="99431-187">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\ClickToRun\REGISTRY\MACHINE\Software\Wow6432Node\Microsoft\Office\16.0\Access 连接 Engine\Engines\Excel**</span><span class="sxs-lookup"><span data-stu-id="99431-187">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\ClickToRun\REGISTRY\MACHINE\Software\Wow6432Node\Microsoft\Office\16.0\Access Connectivity Engine\Engines\Excel**</span></span>

<span data-ttu-id="99431-188">要检查的默认行数为**8** (八)。</span><span class="sxs-lookup"><span data-stu-id="99431-188">The default number of rows to be checked is **8** (eight).</span></span> <span data-ttu-id="99431-189">当您将**TypeGuessRows**值设置为**0** (零) 时, Excel 驱动程序将检查数据类型的前16384行。</span><span class="sxs-lookup"><span data-stu-id="99431-189">When you set the **TypeGuessRows** value to **0** (zero), Excel Driver checks the first 16,384 rows for the data type.</span></span> <span data-ttu-id="99431-190">如果要检查16384以上的行, 请将**TypeGuessRows**设置为基于所需区域的值。</span><span class="sxs-lookup"><span data-stu-id="99431-190">If you want to check more than 16,384 rows, set **TypeGuessRows** to a value that is based on your desired range.</span></span> <span data-ttu-id="99431-191">若要检查所有行, 请将**TypeGuessRows**设置为 1048576 (Excel 中允许的最大行数)。</span><span class="sxs-lookup"><span data-stu-id="99431-191">To check all rows, set **TypeGuessRows** to 1,048,576 (the maximum number of rows that are allowed in Excel).</span></span>
 
<span data-ttu-id="99431-192">数据类型由找到的最大数据类型数决定。</span><span class="sxs-lookup"><span data-stu-id="99431-192">The data type is determined by the maximum number of kinds of data that is found.</span></span> <span data-ttu-id="99431-193">如果有关联, 则按以下顺序确定数据类型:</span><span class="sxs-lookup"><span data-stu-id="99431-193">If there is a tie, the data type is determined in the following order:</span></span>

- <span data-ttu-id="99431-194">帐号</span><span class="sxs-lookup"><span data-stu-id="99431-194">Number</span></span>
- <span data-ttu-id="99431-195">货币</span><span class="sxs-lookup"><span data-stu-id="99431-195">Currency</span></span>
- <span data-ttu-id="99431-196">日期</span><span class="sxs-lookup"><span data-stu-id="99431-196">Date</span></span>
- <span data-ttu-id="99431-197">文本</span><span class="sxs-lookup"><span data-stu-id="99431-197">Text</span></span>
- <span data-ttu-id="99431-198">Boolean</span><span class="sxs-lookup"><span data-stu-id="99431-198">Boolean</span></span>

<span data-ttu-id="99431-199">如果遇到与列的猜测数据类型不匹配的数据, 则该数据以**Null**值的形式返回。</span><span class="sxs-lookup"><span data-stu-id="99431-199">If data is encountered that doesn’t match the guessed data type for the column, that data is returned as a **Null** value.</span></span> <span data-ttu-id="99431-200">在导入过程中, 如果某一列具有混合的数据类型, 则整个列将转换为**ImportMixedTypes**设置所设置的数据类型。</span><span class="sxs-lookup"><span data-stu-id="99431-200">During an import, if a column has mixed data types, the whole column is cast to the data type that’s set by the **ImportMixedTypes** setting.</span></span>

# <a name="office-2013taboffice-2013"></a>[<span data-ttu-id="99431-201">Office 2013</span><span class="sxs-lookup"><span data-stu-id="99431-201">Office 2013</span></span>](#tab/office-2013)

<span data-ttu-id="99431-202">对于在 64 windows 上的32位或64位的 office 上为32位的 office, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="99431-202">For 32-bit Office on 32-bit Windows or 64-bit Office on 64-bit Windows:</span></span>

<span data-ttu-id="99431-203">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Access 连接 Engine\Engines\Excel**</span><span class="sxs-lookup"><span data-stu-id="99431-203">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Access Connectivity Engine\Engines\Excel**</span></span>

<span data-ttu-id="99431-204">对于64位 Windows 上的32位 Office:</span><span class="sxs-lookup"><span data-stu-id="99431-204">For 32-bit Office on 64-bit Windows:</span></span>

<span data-ttu-id="99431-205">**HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Office\15.0\Access 连接 Engine\Engines\Excel**</span><span class="sxs-lookup"><span data-stu-id="99431-205">**HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Office\15.0\Access Connectivity Engine\Engines\Excel**</span></span>

<span data-ttu-id="99431-206">要检查的默认行数为**8** (八)。</span><span class="sxs-lookup"><span data-stu-id="99431-206">The default number of rows to be checked is **8** (eight).</span></span> <span data-ttu-id="99431-207">当您将**TypeGuessRows**值设置为**0** (零) 时, Excel 驱动程序将检查数据类型的前16384行。</span><span class="sxs-lookup"><span data-stu-id="99431-207">When you set the **TypeGuessRows** value to **0** (zero), Excel Driver checks the first 16,384 rows for the data type.</span></span> <span data-ttu-id="99431-208">如果要检查16384以上的行, 请将**TypeGuessRows**设置为基于所需区域的值。</span><span class="sxs-lookup"><span data-stu-id="99431-208">If you want to check more than 16,384 rows, set **TypeGuessRows** to a value that is based on your desired range.</span></span> <span data-ttu-id="99431-209">若要检查所有行, 请将**TypeGuessRows**设置为 1048576 (Excel 中允许的最大行数)。</span><span class="sxs-lookup"><span data-stu-id="99431-209">To check all rows, set **TypeGuessRows** to 1,048,576 (the maximum number of rows that are allowed in Excel).</span></span>
 
<span data-ttu-id="99431-210">数据类型由找到的最大数据类型数决定。</span><span class="sxs-lookup"><span data-stu-id="99431-210">The data type is determined by the maximum number of kinds of data that is found.</span></span> <span data-ttu-id="99431-211">如果有关联, 则按以下顺序确定数据类型:</span><span class="sxs-lookup"><span data-stu-id="99431-211">If there is a tie, the data type is determined in the following order:</span></span>

- <span data-ttu-id="99431-212">帐号</span><span class="sxs-lookup"><span data-stu-id="99431-212">Number</span></span>
- <span data-ttu-id="99431-213">货币</span><span class="sxs-lookup"><span data-stu-id="99431-213">Currency</span></span>
- <span data-ttu-id="99431-214">日期</span><span class="sxs-lookup"><span data-stu-id="99431-214">Date</span></span>
- <span data-ttu-id="99431-215">文本</span><span class="sxs-lookup"><span data-stu-id="99431-215">Text</span></span>
- <span data-ttu-id="99431-216">Boolean</span><span class="sxs-lookup"><span data-stu-id="99431-216">Boolean</span></span>

<span data-ttu-id="99431-217">如果遇到与列的猜测数据类型不匹配的数据, 则该数据以**Null**值的形式返回。</span><span class="sxs-lookup"><span data-stu-id="99431-217">If data is encountered that doesn’t match the guessed data type for the column, that data is returned as a **Null** value.</span></span> <span data-ttu-id="99431-218">在导入过程中, 如果某一列具有混合的数据类型, 则整个列将转换为**ImportMixedTypes**设置所设置的数据类型。</span><span class="sxs-lookup"><span data-stu-id="99431-218">During an import, if a column has mixed data types, the whole column is cast to the data type that’s set by the **ImportMixedTypes** setting.</span></span>

# <a name="office-2010taboffice-2010"></a>[<span data-ttu-id="99431-219">Office 2010</span><span class="sxs-lookup"><span data-stu-id="99431-219">Office 2010</span></span>](#tab/office-2010)

<span data-ttu-id="99431-220">对于在 64 windows 上的32位或64位的 office 上为32位的 office, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="99431-220">For 32-bit Office on 32-bit Windows or 64-bit Office on 64-bit Windows:</span></span>

<span data-ttu-id="99431-221">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Access 连接 Engine\Engines\Excel**</span><span class="sxs-lookup"><span data-stu-id="99431-221">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Access Connectivity Engine\Engines\Excel**</span></span>

<span data-ttu-id="99431-222">对于64位 Windows 上的32位 Office:</span><span class="sxs-lookup"><span data-stu-id="99431-222">For 32-bit Office on 64-bit Windows:</span></span>

<span data-ttu-id="99431-223">**HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Office\15.0\Access 连接 Engine\Engines\Excel**</span><span class="sxs-lookup"><span data-stu-id="99431-223">**HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Office\15.0\Access Connectivity Engine\Engines\Excel**</span></span>

<span data-ttu-id="99431-224">要检查的默认行数为**8** (八)。</span><span class="sxs-lookup"><span data-stu-id="99431-224">The default number of rows to be checked is **8** (eight).</span></span> <span data-ttu-id="99431-225">当您将**TypeGuessRows**值设置为**0** (零) 时, Excel 驱动程序将检查数据类型的前16384行。</span><span class="sxs-lookup"><span data-stu-id="99431-225">When you set the **TypeGuessRows** value to **0** (zero), Excel Driver checks the first 16,384 rows for the data type.</span></span> <span data-ttu-id="99431-226">如果要检查16384以上的行, 请将**TypeGuessRows**设置为基于所需区域的值。</span><span class="sxs-lookup"><span data-stu-id="99431-226">If you want to check more than 16,384 rows, set **TypeGuessRows** to a value that is based on your desired range.</span></span> <span data-ttu-id="99431-227">若要检查所有行, 请将**TypeGuessRows**设置为 1048576 (Excel 中允许的最大行数)。</span><span class="sxs-lookup"><span data-stu-id="99431-227">To check all rows, set **TypeGuessRows** to 1,048,576 (the maximum number of rows that are allowed in Excel).</span></span>
 
<span data-ttu-id="99431-228">数据类型由找到的最大数据类型数决定。</span><span class="sxs-lookup"><span data-stu-id="99431-228">The data type is determined by the maximum number of kinds of data that is found.</span></span> <span data-ttu-id="99431-229">如果有关联, 则按以下顺序确定数据类型:</span><span class="sxs-lookup"><span data-stu-id="99431-229">If there is a tie, the data type is determined in the following order:</span></span>

- <span data-ttu-id="99431-230">帐号</span><span class="sxs-lookup"><span data-stu-id="99431-230">Number</span></span>
- <span data-ttu-id="99431-231">货币</span><span class="sxs-lookup"><span data-stu-id="99431-231">Currency</span></span>
- <span data-ttu-id="99431-232">日期</span><span class="sxs-lookup"><span data-stu-id="99431-232">Date</span></span>
- <span data-ttu-id="99431-233">文本</span><span class="sxs-lookup"><span data-stu-id="99431-233">Text</span></span>
- <span data-ttu-id="99431-234">Boolean</span><span class="sxs-lookup"><span data-stu-id="99431-234">Boolean</span></span>

<span data-ttu-id="99431-235">如果遇到与列的猜测数据类型不匹配的数据, 则该数据以**Null**值的形式返回。</span><span class="sxs-lookup"><span data-stu-id="99431-235">If data is encountered that doesn’t match the guessed data type for the column, that data is returned as a **Null** value.</span></span> <span data-ttu-id="99431-236">在导入过程中, 如果某一列具有混合的数据类型, 则整个列将转换为**ImportMixedTypes**设置所设置的数据类型。</span><span class="sxs-lookup"><span data-stu-id="99431-236">During an import, if a column has mixed data types, the whole column is cast to the data type that’s set by the **ImportMixedTypes** setting.</span></span>

---
> [!NOTE]
> <span data-ttu-id="99431-237">[!注释] 更改 Windows 注册表设置后，必须退出并重新启动数据库引擎，以使新的设置生效。</span><span class="sxs-lookup"><span data-stu-id="99431-237">When you change Windows Registry settings, you must exit and then restart the database engine for the new settings to take effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="99431-238">另请参阅</span><span class="sxs-lookup"><span data-stu-id="99431-238">See also</span></span>

- [<span data-ttu-id="99431-239">使用 Excel 驱动程序的 TypeGuessRows 设置</span><span class="sxs-lookup"><span data-stu-id="99431-239">Using the TypeGuessRows setting for Excel Driver</span></span>](https://support.office.com/en-us/article/using-the-typeguessrows-setting-for-excel-driver-6aa3e101-2a90-47ac-bf0f-7d4109a5708b?ui=en-US&rs=en-US&ad=US)

