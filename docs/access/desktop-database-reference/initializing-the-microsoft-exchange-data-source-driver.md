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
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28704159"
---
# <a name="initializing-the-microsoft-exchange-data-source-driver"></a><span data-ttu-id="fc756-102">初始化 Microsoft Exchange 数据源驱动程序</span><span class="sxs-lookup"><span data-stu-id="fc756-102">Initializing the Microsoft Exchange Data Source driver</span></span>

<span data-ttu-id="fc756-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="fc756-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="fc756-104">当您安装 Microsoft Exchange 数据源驱动程序时，安装程序会将一组默认值写入 Microsoft Windows 注册表中的引擎和 ISAM 格式的子项。</span><span class="sxs-lookup"><span data-stu-id="fc756-104">When you install the Microsoft Exchange Data Source driver, the Setup program writes a set of default values to the Microsoft Windows Registry in the Engines and ISAM Formats subkeys.</span></span> <span data-ttu-id="fc756-105">不应直接修改这些设置，而应使用应用程序的安装程序来添加、删除或更改这些设置。</span><span class="sxs-lookup"><span data-stu-id="fc756-105">You should not modify these settings directly; use the setup program for your application to add, remove, or change these settings.</span></span> <span data-ttu-id="fc756-106">以下各节说明了 Microsoft Exchange 数据源驱动程序的初始化及 ISAM 格式设置。</span><span class="sxs-lookup"><span data-stu-id="fc756-106">The following sections describe initialization and ISAM Format settings for the Microsoft Exchange Data Source driver.</span></span>

## <a name="microsoft-exchange-data-source-initialization-settings"></a><span data-ttu-id="fc756-107">Microsoft Exchange 数据源初始化设置</span><span class="sxs-lookup"><span data-stu-id="fc756-107">Microsoft Exchange data source initialization settings</span></span>

<span data-ttu-id="fc756-108">**Access Connectivity 引擎\\引擎\\Exchange**文件夹包括 Aceexch.dll 驱动程序，用于外部访问 Microsoft Outlook 和 Microsoft Exchange 文件夹的初始化设置。</span><span class="sxs-lookup"><span data-stu-id="fc756-108">The **Access Connectivity Engine\\Engines\\Exchange** folder includes initialization settings for the Aceexch.dll driver, used for external access to Microsoft Outlook and Microsoft Exchange folders.</span></span> <span data-ttu-id="fc756-109">此文件夹中的唯一一项如下所示：</span><span class="sxs-lookup"><span data-stu-id="fc756-109">The only entry in this folder is the following:</span></span>

`win32=<path>\ACEEXCH.DLL`

<span data-ttu-id="fc756-110">Microsoft Access 数据库引擎使用此设置指定 Aceexch.dll 的位置。</span><span class="sxs-lookup"><span data-stu-id="fc756-110">The Microsoft Access database engine uses this setting to indicate the location of Aceexch.dll.</span></span> <span data-ttu-id="fc756-111">其完整路径在安装时确定。</span><span class="sxs-lookup"><span data-stu-id="fc756-111">The full path is determined at the time of installation.</span></span> <span data-ttu-id="fc756-112">注册表类型的值为\_SZ。</span><span class="sxs-lookup"><span data-stu-id="fc756-112">Values are of type REG\_SZ.</span></span>

<span data-ttu-id="fc756-p104">使用 Outlook ISAM 格式和使用 Exchange 客户端 ISAM 格式的效果相似。唯一的区别在于两个不同的客户端为同一列指定不同的名称。这两种 ISAM 格式都已创建，以便 Microsoft Access 数据库引擎能够按用户所需的样式返回列名。</span><span class="sxs-lookup"><span data-stu-id="fc756-p104">The results of using the Outlook ISAM format and of using the Exchange client ISAM format are similar. The only difference is that the two different clients use different names for the same columns. The two ISAM formats have been created so that the Microsoft Access database engine can return the column names in the particular style that the user desires.</span></span>

## <a name="microsoft-outlook-client-isam-formats"></a><span data-ttu-id="fc756-116">Microsoft Outlook 客户端 ISAM 格式</span><span class="sxs-lookup"><span data-stu-id="fc756-116">Microsoft Outlook client ISAM formats</span></span>

<span data-ttu-id="fc756-117">**Access Connectivity 引擎\\ISAM 格式\\Outlook 9.0**文件夹包含下列项。</span><span class="sxs-lookup"><span data-stu-id="fc756-117">The **Access Connectivity Engine\\ISAM Formats\\Outlook 9.0** folder contains the following entries.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="fc756-118">项名</span><span class="sxs-lookup"><span data-stu-id="fc756-118">Entry name</span></span></p></th>
<th><p><span data-ttu-id="fc756-119">类型</span><span class="sxs-lookup"><span data-stu-id="fc756-119">Type</span></span></p></th>
<th><p><span data-ttu-id="fc756-120">值</span><span class="sxs-lookup"><span data-stu-id="fc756-120">Value</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fc756-121">Engine</span><span class="sxs-lookup"><span data-stu-id="fc756-121">Engine</span></span></p></td>
<td><p><span data-ttu-id="fc756-122">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="fc756-122">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="fc756-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="fc756-123">Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc756-124">ImportFilter</span><span class="sxs-lookup"><span data-stu-id="fc756-124">ImportFilter</span></span></p></td>
<td><p><span data-ttu-id="fc756-125">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="fc756-125">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="fc756-126">Outlook()</span><span class="sxs-lookup"><span data-stu-id="fc756-126">Outlook()</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc756-127">CanLink</span><span class="sxs-lookup"><span data-stu-id="fc756-127">CanLink</span></span></p></td>
<td><p><span data-ttu-id="fc756-128">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="fc756-128">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="fc756-129">01</span><span class="sxs-lookup"><span data-stu-id="fc756-129">01</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc756-130">OneTablePerFile</span><span class="sxs-lookup"><span data-stu-id="fc756-130">OneTablePerFile</span></span></p></td>
<td><p><span data-ttu-id="fc756-131">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="fc756-131">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="fc756-132">00</span><span class="sxs-lookup"><span data-stu-id="fc756-132">00</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc756-133">IsamType</span><span class="sxs-lookup"><span data-stu-id="fc756-133">IsamType</span></span></p></td>
<td><p><span data-ttu-id="fc756-134">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="fc756-134">REG_DWORD</span></span></p></td>
<td><p><span data-ttu-id="fc756-135">3</span><span class="sxs-lookup"><span data-stu-id="fc756-135">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc756-136">IndexDialog</span><span class="sxs-lookup"><span data-stu-id="fc756-136">IndexDialog</span></span></p></td>
<td><p><span data-ttu-id="fc756-137">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="fc756-137">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="fc756-138">00</span><span class="sxs-lookup"><span data-stu-id="fc756-138">00</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc756-139">CreateDBOnExport</span><span class="sxs-lookup"><span data-stu-id="fc756-139">CreateDBOnExport</span></span></p></td>
<td><p><span data-ttu-id="fc756-140">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="fc756-140">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="fc756-141">00</span><span class="sxs-lookup"><span data-stu-id="fc756-141">00</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc756-142">SupportsLongNames</span><span class="sxs-lookup"><span data-stu-id="fc756-142">SupportsLongNames</span></span></p></td>
<td><p><span data-ttu-id="fc756-143">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="fc756-143">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="fc756-144">01</span><span class="sxs-lookup"><span data-stu-id="fc756-144">01</span></span></p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <span data-ttu-id="fc756-145">[!注释] 更改 Windows 注册表设置后，必须退出并重新启动数据库引擎，以使新的设置生效。</span><span class="sxs-lookup"><span data-stu-id="fc756-145">When you change Windows Registry settings, you must exit and then restart the database engine for the new settings to take effect.</span></span>



## <a name="microsoft-exchange-client-isam-formats"></a><span data-ttu-id="fc756-146">Microsoft Exchange 客户端 ISAM 格式</span><span class="sxs-lookup"><span data-stu-id="fc756-146">Microsoft Exchange client ISAM formats</span></span>

<span data-ttu-id="fc756-147">**Access Connectivity 引擎\\ISAM 格式\\Exchange 4.0**文件夹包含下列项。</span><span class="sxs-lookup"><span data-stu-id="fc756-147">The **Access Connectivity Engine\\ISAM Formats\\Exchange 4.0** folder contains the following entries.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="fc756-148">项名</span><span class="sxs-lookup"><span data-stu-id="fc756-148">Entry name</span></span></p></th>
<th><p><span data-ttu-id="fc756-149">类型</span><span class="sxs-lookup"><span data-stu-id="fc756-149">Type</span></span></p></th>
<th><p><span data-ttu-id="fc756-150">值</span><span class="sxs-lookup"><span data-stu-id="fc756-150">Value</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fc756-151">Engine</span><span class="sxs-lookup"><span data-stu-id="fc756-151">Engine</span></span></p></td>
<td><p><span data-ttu-id="fc756-152">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="fc756-152">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="fc756-153">Exchange</span><span class="sxs-lookup"><span data-stu-id="fc756-153">Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc756-154">ImportFilter</span><span class="sxs-lookup"><span data-stu-id="fc756-154">ImportFilter</span></span></p></td>
<td><p><span data-ttu-id="fc756-155">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="fc756-155">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="fc756-156">Exchange()</span><span class="sxs-lookup"><span data-stu-id="fc756-156">Exchange()</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc756-157">CanLink</span><span class="sxs-lookup"><span data-stu-id="fc756-157">CanLink</span></span></p></td>
<td><p><span data-ttu-id="fc756-158">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="fc756-158">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="fc756-159">01</span><span class="sxs-lookup"><span data-stu-id="fc756-159">01</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc756-160">OneTablePerFile</span><span class="sxs-lookup"><span data-stu-id="fc756-160">OneTablePerFile</span></span></p></td>
<td><p><span data-ttu-id="fc756-161">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="fc756-161">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="fc756-162">00</span><span class="sxs-lookup"><span data-stu-id="fc756-162">00</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc756-163">IsamType</span><span class="sxs-lookup"><span data-stu-id="fc756-163">IsamType</span></span></p></td>
<td><p><span data-ttu-id="fc756-164">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="fc756-164">REG_DWORD</span></span></p></td>
<td><p><span data-ttu-id="fc756-165">3</span><span class="sxs-lookup"><span data-stu-id="fc756-165">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc756-166">IndexDialog</span><span class="sxs-lookup"><span data-stu-id="fc756-166">IndexDialog</span></span></p></td>
<td><p><span data-ttu-id="fc756-167">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="fc756-167">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="fc756-168">00</span><span class="sxs-lookup"><span data-stu-id="fc756-168">00</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc756-169">CreateDBOnExport</span><span class="sxs-lookup"><span data-stu-id="fc756-169">CreateDBOnExport</span></span></p></td>
<td><p><span data-ttu-id="fc756-170">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="fc756-170">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="fc756-171">00</span><span class="sxs-lookup"><span data-stu-id="fc756-171">00</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc756-172">SupportsLongNames</span><span class="sxs-lookup"><span data-stu-id="fc756-172">SupportsLongNames</span></span></p></td>
<td><p><span data-ttu-id="fc756-173">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="fc756-173">REG_BINARY</span></span></p></td>
<td><p><span data-ttu-id="fc756-174">01</span><span class="sxs-lookup"><span data-stu-id="fc756-174">01</span></span></p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <span data-ttu-id="fc756-175">[!注释] 更改 Windows 注册表设置后，必须退出并重新启动数据库引擎，以使新的设置生效。</span><span class="sxs-lookup"><span data-stu-id="fc756-175">When you change Windows Registry settings, you must exit and then restart the database engine for the new settings to take effect.</span></span>



## <a name="customizing-the-schemaini-file-for-outlook-and-exchange-data"></a><span data-ttu-id="fc756-176">自定义 Outlook 和 Exchange 数据的 Schema.ini 文件</span><span class="sxs-lookup"><span data-stu-id="fc756-176">Customizing the Schema.ini file for Outlook and Exchange data</span></span>

<span data-ttu-id="fc756-p105">Outlook 和 Exchange ISAM 使用 Schema.ini 文件的方式类似于 Text ISAM 使用它的方式。Schema.ini 包含数据源的特定信息：数据的格式以及需要进行访问的列的名称。</span><span class="sxs-lookup"><span data-stu-id="fc756-p105">The Schema.ini file is used by the Outlook and Exchange ISAM in much the same way that it is used by the Text ISAM. Schema.ini contains the specifics of a data source: how the data is formatted, and the names of columns that should be accessed.</span></span>

<span data-ttu-id="fc756-p106">在读取、导入或导出 Outlook 和 Exchange 的数据前，没有必要修改 Schema.ini 文件。Schema.ini 文件中的许多用于 Outlook 和 Exchange 的设置是针对于 MAPI 所需的内部标记的。不要尝试修改这些标记值。</span><span class="sxs-lookup"><span data-stu-id="fc756-p106">It is not necessary to modify the Schema.ini file before data can be read, imported, or exported for Outlook and Exchange. Many of the settings inside the Schema.ini file for Outlook and Exchange are specific to internal tags that MAPI requires. You should not attempt to modify those tag values.</span></span>

