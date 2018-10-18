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
ms.openlocfilehash: 7c9a3282f3bb508a4c68ecbd3f2c0465cfee9bac
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25603096"
---
# <a name="initializing-the-microsoft-excel-driver"></a><span data-ttu-id="ba226-102">初始化 Microsoft Excel 驱动程序</span><span class="sxs-lookup"><span data-stu-id="ba226-102">Initializing the Microsoft Excel Driver</span></span>


<span data-ttu-id="ba226-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="ba226-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="ba226-104"><<<<<<< 标头，当您安装 Microsoft® Excel 驱动程序，安装程序引擎和 ISAM 格式子项中的 Microsoft Windows® 注册表中写入一组默认值。</span><span class="sxs-lookup"><span data-stu-id="ba226-104"><<<<<<< HEAD When you install the Microsoft® Excel driver, the Setup program writes a set of default values to the Microsoft Windows® Registry in the Engines and ISAM Formats subkeys.</span></span> <span data-ttu-id="ba226-105">不应直接修改这些设置，而应使用应用程序的安装程序来添加、删除或更改这些设置。</span><span class="sxs-lookup"><span data-stu-id="ba226-105">You should not modify these settings directly; use the setup program for your application to add, remove, or change these settings.</span></span> <span data-ttu-id="ba226-106">以下各节说明了 Microsoft Excel 数据库驱动程序的初始化和 ISAM 格式设置。</span><span class="sxs-lookup"><span data-stu-id="ba226-106">The following sections describe initialization and ISAM Format settings for the Microsoft Excel database driver.</span></span>

## <a name="microsoft-excel-initialization-settings"></a><span data-ttu-id="ba226-107">Microsoft Excel 初始化设置</span><span class="sxs-lookup"><span data-stu-id="ba226-107">Microsoft Excel Initialization Settings</span></span>
<span data-ttu-id="ba226-108">=== 当您安装 Excel 驱动程序，安装程序引擎和 ISAM 格式子项中在 Windows 注册表中写入一组默认值。</span><span class="sxs-lookup"><span data-stu-id="ba226-108">======= When you install the Excel driver, the Setup program writes a set of default values to the Windows Registry in the Engines and ISAM Formats subkeys.</span></span> <span data-ttu-id="ba226-109">不应直接修改这些设置，而应使用应用程序的安装程序来添加、删除或更改这些设置。</span><span class="sxs-lookup"><span data-stu-id="ba226-109">You should not modify these settings directly; use the setup program for your application to add, remove, or change these settings.</span></span> <span data-ttu-id="ba226-110">以下各节说明了 Microsoft Excel 数据库驱动程序的初始化和 ISAM 格式设置。</span><span class="sxs-lookup"><span data-stu-id="ba226-110">The following sections describe initialization and ISAM Format settings for the Microsoft Excel database driver.</span></span>

## <a name="excel-initialization-settings"></a><span data-ttu-id="ba226-111">Excel 初始化设置</span><span class="sxs-lookup"><span data-stu-id="ba226-111">Excel Initialization Settings</span></span>
>>>>>>> <span data-ttu-id="ba226-112">master</span><span class="sxs-lookup"><span data-stu-id="ba226-112">master</span></span>

<span data-ttu-id="ba226-113">**Access Connectivity 引擎\\引擎\\Excel**文件夹包括 Aceexcl.dll 驱动程序，用于向 Microsoft Excel 工作表的外部访问的初始化设置。</span><span class="sxs-lookup"><span data-stu-id="ba226-113">The **Access Connectivity Engine\\Engines\\Excel** folder includes initialization settings for the Aceexcl.dll driver, used for external access to Microsoft Excel worksheets.</span></span> <span data-ttu-id="ba226-114">下面的示例显示了此文件夹中各项的典型设置。</span><span class="sxs-lookup"><span data-stu-id="ba226-114">Typical settings for the entries in this folder are shown in the following example.</span></span>

```vb
    win32=<path>\ Aceexcl.dll  
    
    TypeGuessRows=8 
    
    ImportMixedTypes=Text 
    
    AppendBlankRows=1 
    
    FirstRowHasNames=Yes
```

<span data-ttu-id="ba226-115">Microsoft Access 数据库引擎使用如下所示的 Excel 文件夹项。</span><span class="sxs-lookup"><span data-stu-id="ba226-115">The Microsoft Access database engine uses the Excel folder entries as follows.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ba226-116">项</span><span class="sxs-lookup"><span data-stu-id="ba226-116">Entry</span></span></p></th>
<th><p><span data-ttu-id="ba226-117">说明</span><span class="sxs-lookup"><span data-stu-id="ba226-117">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba226-118">win32</span><span class="sxs-lookup"><span data-stu-id="ba226-118">win32</span></span></p></td>
<td><p><span data-ttu-id="ba226-p104">msexcl40.dll 的位置。完整路径在安装时确定。值为 REG_SZ 类型。</span><span class="sxs-lookup"><span data-stu-id="ba226-p104">The location of msexcl40.dll. The full path is determined at the time of installation. Values are of type REG_SZ.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba226-122">TypeGuessRows</span><span class="sxs-lookup"><span data-stu-id="ba226-122">TypeGuessRows</span></span></p></td>
<td><p><span data-ttu-id="ba226-p105">确定数据类型时需要检查的行数。数据类型根据找到的数据种类的最大数目确定。如果这样做无效，则按如下顺序确定数据类型：数字、货币、日期、文本、布尔。如果遇到的数据与所猜测的列数据类型不匹配，该数据将作为 <strong>Null</strong> 值返回。在导入时，如果某列使用混合数据类型，则整个列将根据 ImportMixedTypes 设置转换数据类型。 需要检查的默认行数为 8 行。值的类型为 REG_DWORD。  </span><span class="sxs-lookup"><span data-stu-id="ba226-p105">The number of rows to be checked for the data type. The data type is determined given the maximum number of kinds of data found. If there is a tie, the data type is determined in the following order: Number, Currency, Date, Text, Boolean. If data is encountered that does not match the data type guessed for the column, it is returned as a <strong>Null</strong> value. On import, if a column has mixed data types, the entire column will be cast according to the ImportMixedTypes setting. The default number of rows to be checked is 8. Values are of type REG_DWORD.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba226-130">ImportMixedTypes</span><span class="sxs-lookup"><span data-stu-id="ba226-130">ImportMixedTypes</span></span></p></td>
<td><p><span data-ttu-id="ba226-p106">可设为"MajorityType"或"Text"。如果设为"MajorityType"，混合数据类型的列在导入时将强制转换为占优势地位的数据类型。如果设为"Text"，混合数据类型的列在导入时将强制转换为"Text"。默认设置是"Text"。值为 REG_SZ 类型。</span><span class="sxs-lookup"><span data-stu-id="ba226-p106">Can be set to MajorityType or Text. If set to MajorityType, columns of mixed data types will be cast to the predominate data type on import. If set to Text, columns of mixed data types will be cast to Text on import. The default is Text. Values are of type REG_SZ.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba226-136">AppendBlankRows</span><span class="sxs-lookup"><span data-stu-id="ba226-136">AppendBlankRows</span></span></p></td>
<td><p><span data-ttu-id="ba226-p107">在添加新数据前，将追加到 3.5 版或 4.0 版工作表末尾的空白行数。例如，如果 AppendBlankRows 设为 4，Microsoft Jet 将在向工作表追加包含数据的行之前先追加 4 个空白行。此设置的整数值范围可以从 0 到 16。默认值为 01（追加一个附加行）。值为 REG_DWORD 类型。</span><span class="sxs-lookup"><span data-stu-id="ba226-p107">The number of blank rows to be appended to the end of a Version 3.5 or Version 4.0 worksheet before new data is added. For example, if AppendBlankRows is set to 4, Microsoft Jet will append 4 blank rows to the end of the worksheet before appending rows that contain data. Integer values for this setting can range from 0 to 16; the default is 01 (one additional row appended). Values are of type REG_DWORD.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba226-141">FirstRowHasNames</span><span class="sxs-lookup"><span data-stu-id="ba226-141">FirstRowHasNames</span></span></p></td>
<td><p><span data-ttu-id="ba226-p108">指示表的第一行是否包含列名称的二进制值。值 01 指示在导入期间从第一行获取列名称。值 00 指示第一行中没有列名称。列名称显示为 F1、F2、F3 等。默认值为 01。值为 REG_BINARY 类型。</span><span class="sxs-lookup"><span data-stu-id="ba226-p108">A binary value that indicates whether the first row of the table contains column names. A value of 01 indicates that, during import, column names are taken from the first row. A value of 00 indicates no column names in the first row; column names appear as F1, F2, F3, and so on. The default is 01. Values are of type REG_BINARY.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ba226-147">**Access Connectivity 引擎\\引擎\\Excel 8.0**文件夹包含下列项，适用于 Microsoft Excel 97。</span><span class="sxs-lookup"><span data-stu-id="ba226-147">The **Access Connectivity Engine\\Engines\\Excel 8.0** folder contains the following entries, which apply to Microsoft Excel 97.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ba226-148">项名</span><span class="sxs-lookup"><span data-stu-id="ba226-148">Entry name</span></span></p></th>
<th><p><span data-ttu-id="ba226-149">类型</span><span class="sxs-lookup"><span data-stu-id="ba226-149">Type</span></span></p></th>
<th><p><span data-ttu-id="ba226-150">值</span><span class="sxs-lookup"><span data-stu-id="ba226-150">Value</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba226-151">Engine</span><span class="sxs-lookup"><span data-stu-id="ba226-151">Engine</span></span></p></td>
<td><p><span data-ttu-id="ba226-152">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="ba226-152">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="ba226-153">Excel</span><span class="sxs-lookup"><span data-stu-id="ba226-153">Excel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba226-154">ExportFilter</span><span class="sxs-lookup"><span data-stu-id="ba226-154">ExportFilter</span></span></p></td>
<td><p><span data-ttu-id="ba226-155">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="ba226-155">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="ba226-156">Microsoft Excel 97-2000 (\*.xls)</span><span class="sxs-lookup"><span data-stu-id="ba226-156">Microsoft Excel 97-2000 (\*.xls)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba226-157">CanLink</span><span class="sxs-lookup"><span data-stu-id="ba226-157">CanLink</span></span></p></td>
<td><p><span data-ttu-id="ba226-158">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="ba226-158">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="ba226-159">01</span><span class="sxs-lookup"><span data-stu-id="ba226-159">01</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba226-160">OneTablePerFile</span><span class="sxs-lookup"><span data-stu-id="ba226-160">OneTablePerFile</span></span></p></td>
<td><p><span data-ttu-id="ba226-161">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="ba226-161">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="ba226-162">00</span><span class="sxs-lookup"><span data-stu-id="ba226-162">00</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba226-163">IsamType</span><span class="sxs-lookup"><span data-stu-id="ba226-163">IsamType</span></span></p></td>
<td><p><span data-ttu-id="ba226-164">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="ba226-164">REG_DWORD</span></span></p></td>
<td><p><span data-ttu-id="ba226-165">1</span><span class="sxs-lookup"><span data-stu-id="ba226-165">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba226-166">IndexDialog</span><span class="sxs-lookup"><span data-stu-id="ba226-166">IndexDialog</span></span></p></td>
<td><p><span data-ttu-id="ba226-167">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="ba226-167">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="ba226-168">00</span><span class="sxs-lookup"><span data-stu-id="ba226-168">00</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba226-169">CreateDBOnExport</span><span class="sxs-lookup"><span data-stu-id="ba226-169">CreateDBOnExport</span></span></p></td>
<td><p><span data-ttu-id="ba226-170">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="ba226-170">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="ba226-171">01</span><span class="sxs-lookup"><span data-stu-id="ba226-171">01</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba226-172">ResultTextExport</span><span class="sxs-lookup"><span data-stu-id="ba226-172">ResultTextExport</span></span></p></td>
<td><p><span data-ttu-id="ba226-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="ba226-173">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="ba226-p109">将数据从当前数据库导出到 Microsoft Excel 97 文件。如果导出到现有文件，此过程将覆盖数据。</span><span class="sxs-lookup"><span data-stu-id="ba226-p109">Export data from the current database into a Microsoft Excel 97 file. This process will overwrite the data if exported to an existing file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba226-176">SupportsLongNames</span><span class="sxs-lookup"><span data-stu-id="ba226-176">SupportsLongNames</span></span></p></td>
<td><p><span data-ttu-id="ba226-177">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="ba226-177">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="ba226-178">01</span><span class="sxs-lookup"><span data-stu-id="ba226-178">01</span></span></p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <span data-ttu-id="ba226-179">[!注释] 更改 Windows 注册表设置后，必须退出并重新启动数据库引擎，以使新的设置生效。</span><span class="sxs-lookup"><span data-stu-id="ba226-179">When you change Windows Registry settings, you must exit and then restart the database engine for the new settings to take effect.</span></span>

<span data-ttu-id="ba226-180"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="ba226-180"><<<<<<< HEAD</span></span>

=======
## <a name="see-also"></a><span data-ttu-id="ba226-181">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba226-181">See also</span></span>

[<span data-ttu-id="ba226-182">使用 Excel 驱动程序 TypeGuessRows 设置</span><span class="sxs-lookup"><span data-stu-id="ba226-182">Using the TypeGuessRows setting for Excel Driver</span></span>](https://support.office.com/en-us/article/using-the-typeguessrows-setting-for-excel-driver-6aa3e101-2a90-47ac-bf0f-7d4109a5708b?ui=en-US&rs=en-US&ad=US)
>>>>>>> <span data-ttu-id="ba226-183">master</span><span class="sxs-lookup"><span data-stu-id="ba226-183">master</span></span>
