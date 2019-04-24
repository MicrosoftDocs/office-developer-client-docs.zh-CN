---
title: HelloData：简单 ADO 应用程序
TOCTitle: 'HelloData: A simple ADO application'
ms:assetid: c271abeb-8865-81f9-db8e-47d3db87ad30
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249950(v=office.15)
ms:contentKeyID: 48547554
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 3c7d9be9b91b3f847516eb3c22aa37e46c8a551d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292018"
---
# <a name="hellodata-a-simple-ado-application"></a><span data-ttu-id="2c79c-102">HelloData：简单 ADO 应用程序</span><span class="sxs-lookup"><span data-stu-id="2c79c-102">HelloData: A simple ADO application</span></span>

<span data-ttu-id="2c79c-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="2c79c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="2c79c-p101">若要奠定探索 ADO 库的基础，可以考虑使用名"HelloData"的简单 ADO 应用程序。HelloData 分步介绍了四种主要 ADO 操作（获取数据、检查数据、编辑数据和更新数据）中的每一种。为了注重 ADO 基础并避免出现代码混乱，示例中进行了最少错误处理。</span><span class="sxs-lookup"><span data-stu-id="2c79c-p101">To lay the groundwork for an exploration of the ADO library, consider a simple ADO application called "HelloData." HelloData steps through each of the four major ADO operations (getting, examining, editing, and updating data). In order to focus on the fundamentals of ADO and prevent code clutter, minimal error handling is done in the example.</span></span>

<span data-ttu-id="2c79c-107">该应用程序查询 Microsoft SQL Server 2000 中包含的罗斯文示例数据库。</span><span class="sxs-lookup"><span data-stu-id="2c79c-107">The application queries the Northwind sample database that is included with Microsoft SQL Server 2000.</span></span>

<span data-ttu-id="2c79c-108">**运行 HelloData**</span><span class="sxs-lookup"><span data-stu-id="2c79c-108">**To run HelloData**</span></span>

1.  <span data-ttu-id="2c79c-109">新建一个引用 ADO 2.5 库的标准可执行 Visual Basic 项目。</span><span class="sxs-lookup"><span data-stu-id="2c79c-109">Create a new Standard Executable Visual Basic Project that references the ADO 2.5 library.</span></span>

2.  <span data-ttu-id="2c79c-110">在窗体顶部创建四个命令按钮，将 **Name** 和 **Caption** 属性设置为下表中所示的值。</span><span class="sxs-lookup"><span data-stu-id="2c79c-110">Create four command buttons at the top of the form, setting the **Name** and **Caption** properties to the values shown in the table below.</span></span>

3.  <span data-ttu-id="2c79c-111">在按钮下方，添加 **Microsoft DataGrid Control** (Msdatgrd.ocx)。</span><span class="sxs-lookup"><span data-stu-id="2c79c-111">Below the buttons, add a **Microsoft DataGrid Control** (Msdatgrd.ocx).</span></span> <span data-ttu-id="2c79c-112">Msdatgrd 文件包含在 Visual Basic 中, \\位于 windows\\system32 或\\winnt\\system32 目录中。</span><span class="sxs-lookup"><span data-stu-id="2c79c-112">The Msdatgrd.ocx file comes with Visual Basic and is located in your \\windows\\system32 or \\winnt\\system32 directory.</span></span> <span data-ttu-id="2c79c-113">若要向 Visual Basic 工具箱面板添加 DataGrid 控件，请从“工程”菜单上选择“组件”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c79c-113">To add the DataGrid control to your Visual Basic toolbox pane, select **Components...** from the **Project** menu.</span></span> <span data-ttu-id="2c79c-114">选中“Microsoft DataGrid Control 6.0 (SP3) (OLEDB)”旁边的复选框，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c79c-114">Then check the box next to "Microsoft DataGrid Control 6.0 (SP3) (OLEDB)" and click **OK**.</span></span> <span data-ttu-id="2c79c-115">若要向工程添加控件，请将 DataGrid 控件从工具箱拖到 Visual Basic 窗体上。</span><span class="sxs-lookup"><span data-stu-id="2c79c-115">To add the control to the project, drag the DataGrid control from the Toolbox to the Visual Basic form.</span></span>

4.  <span data-ttu-id="2c79c-p103">在网格下方的窗体上创建一个 **文本框** ，按表中所示设置其属性。完成时，该窗体的外观应如下图所示。</span><span class="sxs-lookup"><span data-stu-id="2c79c-p103">Create a **TextBox** on the form below the grid and set its properties as shown in the table. The form should look similar to the following figure when you are finished.</span></span>

5.  <span data-ttu-id="2c79c-118">最后, 将[HelloData 代码](hellodata-code.md)中列出的代码复制并粘贴到窗体的代码编辑器窗口中。</span><span class="sxs-lookup"><span data-stu-id="2c79c-118">Finally, copy the code listed in [HelloData Code](hellodata-code.md) and paste it into the code editor window of the form.</span></span> <span data-ttu-id="2c79c-119">按 **F5** 运行代码。</span><span class="sxs-lookup"><span data-stu-id="2c79c-119">Press **F5** to run the code.</span></span>

> [!NOTE]
> <span data-ttu-id="2c79c-p105">[!注释] 在以下示例和整个指南中，将以用户 ID"MyId"和密码"123aBc"来向服务器进行身份验证。应当用您的服务器的有效登录凭据来替换这些值，并用您的服务器的名称替换"MyServer"值。</span><span class="sxs-lookup"><span data-stu-id="2c79c-p105">In the following example, and throughout the guide, the user id "MyId" with a password of "123aBc" is used to authenticate against the server. You should substitute these values with valid logon credentials for your server. Also, substitute the "MyServer" value with the name of your server.</span></span>

<span data-ttu-id="2c79c-123">有关代码的详细说明, 请参阅[HelloData Details](hellodata-details.md)。</span><span class="sxs-lookup"><span data-stu-id="2c79c-123">For a detailed description of the code, see [HelloData Details](hellodata-details.md).</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="2c79c-124">控件类型</span><span class="sxs-lookup"><span data-stu-id="2c79c-124">Control Type</span></span></p></th>
<th><p><span data-ttu-id="2c79c-125">属性</span><span class="sxs-lookup"><span data-stu-id="2c79c-125">Property</span></span></p></th>
<th><p><span data-ttu-id="2c79c-126">值</span><span class="sxs-lookup"><span data-stu-id="2c79c-126">Value</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2c79c-127">窗体</span><span class="sxs-lookup"><span data-stu-id="2c79c-127">Form</span></span></p></td>
<td><p><span data-ttu-id="2c79c-128">名称</span><span class="sxs-lookup"><span data-stu-id="2c79c-128">Name</span></span></p></td>
<td><p><span data-ttu-id="2c79c-129">Form1</span><span class="sxs-lookup"><span data-stu-id="2c79c-129">Form1</span></span></p></td>
</tr>
<tr class="even">
<td><p><br />
</p></td>
<td><p><span data-ttu-id="2c79c-130">Height</span><span class="sxs-lookup"><span data-stu-id="2c79c-130">Height</span></span></p></td>
<td><p><span data-ttu-id="2c79c-131">6500</span><span class="sxs-lookup"><span data-stu-id="2c79c-131">6500</span></span></p></td>
</tr>
<tr class="odd">
<td><p><br />
</p></td>
<td><p><span data-ttu-id="2c79c-132">Width</span><span class="sxs-lookup"><span data-stu-id="2c79c-132">Width</span></span></p></td>
<td><p><span data-ttu-id="2c79c-133">6500</span><span class="sxs-lookup"><span data-stu-id="2c79c-133">6500</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c79c-134">MS 数据网格</span><span class="sxs-lookup"><span data-stu-id="2c79c-134">MS DataGrid</span></span></p></td>
<td><p><span data-ttu-id="2c79c-135">名称</span><span class="sxs-lookup"><span data-stu-id="2c79c-135">Name</span></span></p></td>
<td><p><span data-ttu-id="2c79c-136">grdDisplay1</span><span class="sxs-lookup"><span data-stu-id="2c79c-136">grdDisplay1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c79c-137">TextBox</span><span class="sxs-lookup"><span data-stu-id="2c79c-137">TextBox</span></span></p></td>
<td><p><span data-ttu-id="2c79c-138">名称</span><span class="sxs-lookup"><span data-stu-id="2c79c-138">Name</span></span></p></td>
<td><p><span data-ttu-id="2c79c-139">txtDisplay1</span><span class="sxs-lookup"><span data-stu-id="2c79c-139">txtDisplay1</span></span></p></td>
</tr>
<tr class="even">
<td><p><br />
</p></td>
<td><p><span data-ttu-id="2c79c-140">适用</span><span class="sxs-lookup"><span data-stu-id="2c79c-140">Multiline</span></span></p></td>
<td><p><span data-ttu-id="2c79c-141">true</span><span class="sxs-lookup"><span data-stu-id="2c79c-141">true</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c79c-142">命令按钮</span><span class="sxs-lookup"><span data-stu-id="2c79c-142">Command Button</span></span></p></td>
<td><p><span data-ttu-id="2c79c-143">名称</span><span class="sxs-lookup"><span data-stu-id="2c79c-143">Name</span></span></p></td>
<td><p><span data-ttu-id="2c79c-144">cmdGetData</span><span class="sxs-lookup"><span data-stu-id="2c79c-144">cmdGetData</span></span></p></td>
</tr>
<tr class="even">
<td><p><br />
</p></td>
<td><p><span data-ttu-id="2c79c-145">Caption</span><span class="sxs-lookup"><span data-stu-id="2c79c-145">Caption</span></span></p></td>
<td><p><span data-ttu-id="2c79c-146">获取数据</span><span class="sxs-lookup"><span data-stu-id="2c79c-146">Get Data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c79c-147">命令按钮</span><span class="sxs-lookup"><span data-stu-id="2c79c-147">Command Button</span></span></p></td>
<td><p><span data-ttu-id="2c79c-148">名称</span><span class="sxs-lookup"><span data-stu-id="2c79c-148">Name</span></span></p></td>
<td><p><span data-ttu-id="2c79c-149">cmdExamineData</span><span class="sxs-lookup"><span data-stu-id="2c79c-149">cmdExamineData</span></span></p></td>
</tr>
<tr class="even">
<td><p><br />
</p></td>
<td><p><span data-ttu-id="2c79c-150">Caption</span><span class="sxs-lookup"><span data-stu-id="2c79c-150">Caption</span></span></p></td>
<td><p><span data-ttu-id="2c79c-151">检查数据</span><span class="sxs-lookup"><span data-stu-id="2c79c-151">Examine Data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c79c-152">命令按钮</span><span class="sxs-lookup"><span data-stu-id="2c79c-152">Command Button</span></span></p></td>
<td><p><span data-ttu-id="2c79c-153">名称</span><span class="sxs-lookup"><span data-stu-id="2c79c-153">Name</span></span></p></td>
<td><p><span data-ttu-id="2c79c-154">cmdEditData</span><span class="sxs-lookup"><span data-stu-id="2c79c-154">cmdEditData</span></span></p></td>
</tr>
<tr class="even">
<td><p><br />
</p></td>
<td><p><span data-ttu-id="2c79c-155">Caption</span><span class="sxs-lookup"><span data-stu-id="2c79c-155">Caption</span></span></p></td>
<td><p><span data-ttu-id="2c79c-156">编辑数据</span><span class="sxs-lookup"><span data-stu-id="2c79c-156">Edit Data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c79c-157">命令按钮</span><span class="sxs-lookup"><span data-stu-id="2c79c-157">Command Button</span></span></p></td>
<td><p><span data-ttu-id="2c79c-158">名称</span><span class="sxs-lookup"><span data-stu-id="2c79c-158">Name</span></span></p></td>
<td><p><span data-ttu-id="2c79c-159">cmdUpdateData</span><span class="sxs-lookup"><span data-stu-id="2c79c-159">cmdUpdateData</span></span></p></td>
</tr>
<tr class="even">
<td><p><br />
</p></td>
<td><p><span data-ttu-id="2c79c-160">Caption</span><span class="sxs-lookup"><span data-stu-id="2c79c-160">Caption</span></span></p></td>
<td><p><span data-ttu-id="2c79c-161">更新数据</span><span class="sxs-lookup"><span data-stu-id="2c79c-161">Update Data</span></span></p></td>
</tr>
</tbody>
</table>



