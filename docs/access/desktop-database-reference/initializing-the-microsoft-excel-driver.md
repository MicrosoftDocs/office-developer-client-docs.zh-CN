---
title: 初始化 Microsoft Excel 驱动程序
TOCTitle: Initializing the Microsoft Excel Driver
ms:assetid: 06c7f823-8e74-0811-cc00-e6b32075ef11
ms:mtpsurl: https://msdn.microsoft.com/library/Ff844939(v=office.15)
ms:contentKeyID: 48543054
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- acmain11.chm1032159
f1_categories:
- Office.Version=v15
ms.openlocfilehash: c79d859b122eb3595c31b2ffcec192e2d69ed7b4
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468597"
---
# <a name="initializing-the-microsoft-excel-driver"></a><span data-ttu-id="54732-102">初始化 Microsoft Excel 驱动程序</span><span class="sxs-lookup"><span data-stu-id="54732-102">Initializing the Microsoft Excel Driver</span></span>


<span data-ttu-id="54732-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="54732-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="54732-p101">安装 Microsoft® Excel 驱动程序时，安装程序会将一组默认值写入 Microsoft Windows® 注册表中的"Engines"和"ISAM Formats"子项。不应直接修改这些设置，而应使用应用程序的安装程序来添加、删除或更改这些设置。以下各节说明了 Microsoft Excel 数据库驱动程序的初始化和 ISAM 格式设置。</span><span class="sxs-lookup"><span data-stu-id="54732-p101">When you install the Microsoft® Excel driver, the Setup program writes a set of default values to the Microsoft Windows® Registry in the Engines and ISAM Formats subkeys. You should not modify these settings directly; use the setup program for your application to add, remove, or change these settings. The following sections describe initialization and ISAM Format settings for the Microsoft Excel database driver.</span></span>

## <a name="microsoft-excel-initialization-settings"></a><span data-ttu-id="54732-107">Microsoft Excel 初始化设置</span><span class="sxs-lookup"><span data-stu-id="54732-107">Microsoft Excel Initialization Settings</span></span>

<span data-ttu-id="54732-108">**Access Connectivity 引擎\\引擎\\Excel**文件夹包括 Aceexcl.dll 驱动程序，用于向 Microsoft Excel 工作表的外部访问的初始化设置。</span><span class="sxs-lookup"><span data-stu-id="54732-108">The **Access Connectivity Engine\\Engines\\Excel** folder includes initialization settings for the Aceexcl.dll driver, used for external access to Microsoft Excel worksheets.</span></span> <span data-ttu-id="54732-109">下面的示例显示了此文件夹中各项的典型设置。</span><span class="sxs-lookup"><span data-stu-id="54732-109">Typical settings for the entries in this folder are shown in the following example.</span></span>

```vb
    win32=<path>\ Aceexcl.dll  
    
    TypeGuessRows=8 
    
    ImportMixedTypes=Text 
    
    AppendBlankRows=1 
    
    FirstRowHasNames=Yes
```

<span data-ttu-id="54732-110">Microsoft Access 数据库引擎使用如下所示的 Excel 文件夹项。</span><span class="sxs-lookup"><span data-stu-id="54732-110">The Microsoft Access database engine uses the Excel folder entries as follows.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="54732-111">项</span><span class="sxs-lookup"><span data-stu-id="54732-111">Entry</span></span></p></th>
<th><p><span data-ttu-id="54732-112">说明</span><span class="sxs-lookup"><span data-stu-id="54732-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54732-113">win32</span><span class="sxs-lookup"><span data-stu-id="54732-113">win32</span></span></p></td>
<td><p><span data-ttu-id="54732-p103">msexcl40.dll 的位置。完整路径在安装时确定。值为 REG_SZ 类型。</span><span class="sxs-lookup"><span data-stu-id="54732-p103">The location of msexcl40.dll. The full path is determined at the time of installation. Values are of type REG_SZ.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54732-117">TypeGuessRows</span><span class="sxs-lookup"><span data-stu-id="54732-117">TypeGuessRows</span></span></p></td>
<td><p><span data-ttu-id="54732-p104">确定数据类型时需要检查的行数。数据类型根据找到的数据种类的最大数目确定。如果这样做无效，则按如下顺序确定数据类型：数字、货币、日期、文本、布尔。如果遇到的数据与所猜测的列数据类型不匹配，该数据将作为 <strong>Null</strong> 值返回。在导入时，如果某列使用混合数据类型，则整个列将根据 ImportMixedTypes 设置转换数据类型。 需要检查的默认行数为 8 行。值的类型为 REG_DWORD。  </span><span class="sxs-lookup"><span data-stu-id="54732-p104">The number of rows to be checked for the data type. The data type is determined given the maximum number of kinds of data found. If there is a tie, the data type is determined in the following order: Number, Currency, Date, Text, Boolean. If data is encountered that does not match the data type guessed for the column, it is returned as a <strong>Null</strong> value. On import, if a column has mixed data types, the entire column will be cast according to the ImportMixedTypes setting. The default number of rows to be checked is 8. Values are of type REG_DWORD.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54732-125">ImportMixedTypes</span><span class="sxs-lookup"><span data-stu-id="54732-125">ImportMixedTypes</span></span></p></td>
<td><p><span data-ttu-id="54732-p105">可设为"MajorityType"或"Text"。如果设为"MajorityType"，混合数据类型的列在导入时将强制转换为占优势地位的数据类型。如果设为"Text"，混合数据类型的列在导入时将强制转换为"Text"。默认设置是"Text"。值为 REG_SZ 类型。</span><span class="sxs-lookup"><span data-stu-id="54732-p105">Can be set to MajorityType or Text. If set to MajorityType, columns of mixed data types will be cast to the predominate data type on import. If set to Text, columns of mixed data types will be cast to Text on import. The default is Text. Values are of type REG_SZ.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54732-131">AppendBlankRows</span><span class="sxs-lookup"><span data-stu-id="54732-131">AppendBlankRows</span></span></p></td>
<td><p><span data-ttu-id="54732-p106">在添加新数据前，将追加到 3.5 版或 4.0 版工作表末尾的空白行数。例如，如果 AppendBlankRows 设为 4，Microsoft Jet 将在向工作表追加包含数据的行之前先追加 4 个空白行。此设置的整数值范围可以从 0 到 16。默认值为 01（追加一个附加行）。值为 REG_DWORD 类型。</span><span class="sxs-lookup"><span data-stu-id="54732-p106">The number of blank rows to be appended to the end of a Version 3.5 or Version 4.0 worksheet before new data is added. For example, if AppendBlankRows is set to 4, Microsoft Jet will append 4 blank rows to the end of the worksheet before appending rows that contain data. Integer values for this setting can range from 0 to 16; the default is 01 (one additional row appended). Values are of type REG_DWORD.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54732-136">FirstRowHasNames</span><span class="sxs-lookup"><span data-stu-id="54732-136">FirstRowHasNames</span></span></p></td>
<td><p><span data-ttu-id="54732-p107">指示表的第一行是否包含列名称的二进制值。值 01 指示在导入期间从第一行获取列名称。值 00 指示第一行中没有列名称。列名称显示为 F1、F2、F3 等。默认值为 01。值为 REG_BINARY 类型。</span><span class="sxs-lookup"><span data-stu-id="54732-p107">A binary value that indicates whether the first row of the table contains column names. A value of 01 indicates that, during import, column names are taken from the first row. A value of 00 indicates no column names in the first row; column names appear as F1, F2, F3, and so on. The default is 01. Values are of type REG_BINARY.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="54732-142">**Access Connectivity 引擎\\引擎\\Excel 8.0**文件夹包含下列项，适用于 Microsoft Excel 97。</span><span class="sxs-lookup"><span data-stu-id="54732-142">The **Access Connectivity Engine\\Engines\\Excel 8.0** folder contains the following entries, which apply to Microsoft Excel 97.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="54732-143">项名</span><span class="sxs-lookup"><span data-stu-id="54732-143">Entry name</span></span></p></th>
<th><p><span data-ttu-id="54732-144">类型</span><span class="sxs-lookup"><span data-stu-id="54732-144">Type</span></span></p></th>
<th><p><span data-ttu-id="54732-145">值</span><span class="sxs-lookup"><span data-stu-id="54732-145">Value</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54732-146">Engine</span><span class="sxs-lookup"><span data-stu-id="54732-146">Engine</span></span></p></td>
<td><p><span data-ttu-id="54732-147">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="54732-147">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="54732-148">Excel</span><span class="sxs-lookup"><span data-stu-id="54732-148">Excel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54732-149">ExportFilter</span><span class="sxs-lookup"><span data-stu-id="54732-149">ExportFilter</span></span></p></td>
<td><p><span data-ttu-id="54732-150">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="54732-150">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="54732-151">Microsoft Excel 97-2000 (\*.xls)</span><span class="sxs-lookup"><span data-stu-id="54732-151">Microsoft Excel 97-2000 (\*.xls)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54732-152">CanLink</span><span class="sxs-lookup"><span data-stu-id="54732-152">CanLink</span></span></p></td>
<td><p><span data-ttu-id="54732-153">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="54732-153">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="54732-154">01</span><span class="sxs-lookup"><span data-stu-id="54732-154">01</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54732-155">OneTablePerFile</span><span class="sxs-lookup"><span data-stu-id="54732-155">OneTablePerFile</span></span></p></td>
<td><p><span data-ttu-id="54732-156">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="54732-156">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="54732-157">00</span><span class="sxs-lookup"><span data-stu-id="54732-157">00</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54732-158">IsamType</span><span class="sxs-lookup"><span data-stu-id="54732-158">IsamType</span></span></p></td>
<td><p><span data-ttu-id="54732-159">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="54732-159">REG_DWORD</span></span></p></td>
<td><p><span data-ttu-id="54732-160">1</span><span class="sxs-lookup"><span data-stu-id="54732-160">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54732-161">IndexDialog</span><span class="sxs-lookup"><span data-stu-id="54732-161">IndexDialog</span></span></p></td>
<td><p><span data-ttu-id="54732-162">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="54732-162">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="54732-163">00</span><span class="sxs-lookup"><span data-stu-id="54732-163">00</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54732-164">CreateDBOnExport</span><span class="sxs-lookup"><span data-stu-id="54732-164">CreateDBOnExport</span></span></p></td>
<td><p><span data-ttu-id="54732-165">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="54732-165">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="54732-166">01</span><span class="sxs-lookup"><span data-stu-id="54732-166">01</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54732-167">ResultTextExport</span><span class="sxs-lookup"><span data-stu-id="54732-167">ResultTextExport</span></span></p></td>
<td><p><span data-ttu-id="54732-168">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="54732-168">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="54732-p108">将数据从当前数据库导出到 Microsoft Excel 97 文件。如果导出到现有文件，此过程将覆盖数据。</span><span class="sxs-lookup"><span data-stu-id="54732-p108">Export data from the current database into a Microsoft Excel 97 file. This process will overwrite the data if exported to an existing file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54732-171">SupportsLongNames</span><span class="sxs-lookup"><span data-stu-id="54732-171">SupportsLongNames</span></span></p></td>
<td><p><span data-ttu-id="54732-172">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="54732-172">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="54732-173">01</span><span class="sxs-lookup"><span data-stu-id="54732-173">01</span></span></p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <span data-ttu-id="54732-174">[!注释] 更改 Windows 注册表设置后，必须退出并重新启动数据库引擎，以使新的设置生效。</span><span class="sxs-lookup"><span data-stu-id="54732-174">When you change Windows Registry settings, you must exit and then restart the database engine for the new settings to take effect.</span></span>


