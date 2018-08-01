---
title: 创建 COM 加载项并将自定义功能添加到 InfoPath
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
keywords:
- infopath 2007 中，创建 com 加载项，InfoPath 2007 添加自定义功能，COM 加载项 [InfoPath 2007]
localization_priority: Normal
ms.assetid: af0b0bc9-20ef-4503-8b3b-8f2a97b671a2
description: Microsoft InfoPath 支持 COM 加载项扩展窗体编辑的用户体验。 尽管支持的如 Microsoft Office Word 和 Microsoft Office Excel 具有 Office 2000 以来支持 COM 加载项首先 COM 加载项添加 InfoPath，其他 Office 应用程序中。
ms.openlocfilehash: 4c70dfb71cf7b15a0978b4567ffac02a8ba524c3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773882"
---
# <a name="create-a-com-add-in-to-add-custom-features-to-infopath"></a><span data-ttu-id="edfbd-105">创建 COM 加载项并将自定义功能添加到 InfoPath</span><span class="sxs-lookup"><span data-stu-id="edfbd-105">Create a COM Add-in to Add Custom Features to InfoPath</span></span>

<span data-ttu-id="edfbd-106">Microsoft InfoPath 支持 COM 加载项扩展窗体编辑的用户体验。</span><span class="sxs-lookup"><span data-stu-id="edfbd-106">Microsoft InfoPath supports COM Add-ins for extending the form editing user experience.</span></span> <span data-ttu-id="edfbd-107">尽管支持的如 Microsoft Office Word 和 Microsoft Office Excel 具有 Office 2000 以来支持 COM 加载项首先 COM 加载项添加 InfoPath，其他 Office 应用程序中。</span><span class="sxs-lookup"><span data-stu-id="edfbd-107">Although support for COM Add-ins was first added in InfoPath, other Office applications such as Microsoft Office Word and Microsoft Office Excel have supported COM add-ins since Office 2000.</span></span>
  
<span data-ttu-id="edfbd-108">可用于表单环境寄宿在 InfoPath 中的 COM 加载项支持。</span><span class="sxs-lookup"><span data-stu-id="edfbd-108">COM Add-in support in InfoPath is available for the form editing environment.</span></span> <span data-ttu-id="edfbd-109">无法使用 COM 加载项扩展窗体设计环境。</span><span class="sxs-lookup"><span data-stu-id="edfbd-109">The form design environment cannot be extended by using COM Add-ins.</span></span>
  
## <a name="the-idtextensibility2-interface"></a><span data-ttu-id="edfbd-110">IDTExtensibility2 接口</span><span class="sxs-lookup"><span data-stu-id="edfbd-110">The IDTExtensibility2 Interface</span></span>

<span data-ttu-id="edfbd-111">编辑环境提供支持**IDTExtensibility2**接口，必须由开发人员的 COM 加载宏**IDTExtensibility2**实现 InfoPath 是一个双接口对象，提供了五种用作事件的方法在编辑的环境。</span><span class="sxs-lookup"><span data-stu-id="edfbd-111">The InfoPath editing environment provides support for the **IDTExtensibility2** interface, which must be implemented by developers of COM Add-ins. **IDTExtensibility2** is a dual-interface object that provides five methods which act as events within the editing environment.</span></span> <span data-ttu-id="edfbd-112">COM 加载项以响应环境启动和关机条件下, 表中列出允许这些方法。</span><span class="sxs-lookup"><span data-stu-id="edfbd-112">These methods allow the COM add-in to respond to environment startup and shutdown conditions, listed in the following table.</span></span> 
  
|<span data-ttu-id="edfbd-113">**接口**</span><span class="sxs-lookup"><span data-stu-id="edfbd-113">**Interface**</span></span>|<span data-ttu-id="edfbd-114">**说明**</span><span class="sxs-lookup"><span data-stu-id="edfbd-114">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="edfbd-115">**OnAddInsUpdate (ByVal custom() 为 Variant)**</span><span class="sxs-lookup"><span data-stu-id="edfbd-115">**OnAddInsUpdate (ByVal custom() As Variant)**</span></span> <br/> |<span data-ttu-id="edfbd-116">外接程序是加载或卸载环境中时，发生此事件。</span><span class="sxs-lookup"><span data-stu-id="edfbd-116">Occurs when an add-in is loaded or unloaded in the environment.</span></span>  <br/> |
|<span data-ttu-id="edfbd-117">**OnBeginShutdown (ByVal custom() 为 Variant)**</span><span class="sxs-lookup"><span data-stu-id="edfbd-117">**OnBeginShutdown (ByVal custom() As Variant)**</span></span> <br/> |<span data-ttu-id="edfbd-118">正在关闭环境时，发生此事件。</span><span class="sxs-lookup"><span data-stu-id="edfbd-118">Occurs when the environment is being shut down.</span></span>  <br/> |
|<span data-ttu-id="edfbd-119">**OnConnection （ByVal 应用程序作为对象，ByVal ConnectMode As ext_ConnectMode，ByVal AddInInst As Object，ByVal custom() 为 Variant）**</span><span class="sxs-lookup"><span data-stu-id="edfbd-119">**OnConnection(ByVal Application As Object, ByVal ConnectMode As ext_ConnectMode, ByVal AddInInst As Object, ByVal custom() As Variant)**</span></span> <br/> |<span data-ttu-id="edfbd-120">加载在环境中的外接程序时，发生此事件。</span><span class="sxs-lookup"><span data-stu-id="edfbd-120">Occurs when an add-in is loaded in the environment.</span></span>  <br/> |
|<span data-ttu-id="edfbd-121">**OnDisconnection (ByVal 如果 RemoveMode As ext_DisconnectMode，ByVal custom() 为 Variant)**</span><span class="sxs-lookup"><span data-stu-id="edfbd-121">**OnDisconnection (ByVal RemoveMode As ext_DisconnectMode, ByVal custom() As Variant)**</span></span> <br/> |<span data-ttu-id="edfbd-122">外接程序是从环境中卸载时发生。</span><span class="sxs-lookup"><span data-stu-id="edfbd-122">Occurs when an add-in is unloaded from the environment.</span></span>  <br/> |
|<span data-ttu-id="edfbd-123">**OnStartupComplete (ByVal custom() 为 Variant)**</span><span class="sxs-lookup"><span data-stu-id="edfbd-123">**OnStartupComplete (ByVal custom() As Variant)**</span></span> <br/> |<span data-ttu-id="edfbd-124">当环境已完成启动时，发生此事件。</span><span class="sxs-lookup"><span data-stu-id="edfbd-124">Occurs when the environment has completed starting.</span></span>  <br/> |
   
## <a name="registering-com-add-ins"></a><span data-ttu-id="edfbd-125">注册 COM 加载项</span><span class="sxs-lookup"><span data-stu-id="edfbd-125">Registering COM Add-ins</span></span>

<span data-ttu-id="edfbd-126">所有 Office 应用程序，包括 InfoPath 都使用到列表中的加载项的 COM 加载项集合，注册表用于存储连接状态，并存储启动或需求加载信息。</span><span class="sxs-lookup"><span data-stu-id="edfbd-126">All Office applications, including InfoPath, use the registry to list add-ins in the COM Add-Ins collection, to store the connect state, and to store the boot or demand load information.</span></span> <span data-ttu-id="edfbd-127">为 InfoPath COM 加载项，每一加载项的名称将出现在以下项下：</span><span class="sxs-lookup"><span data-stu-id="edfbd-127">For InfoPath COM Add-ins, the name of each add-in appears under the following key:</span></span>
  
`HKEY_CURRENT_USER\Software\Microsoft\Office\InfoPath\AddIns\`
  
<span data-ttu-id="edfbd-128">COM 加载项以供客户端计算机的每个用户安装注册表项位于 HKLM 注册表配置单元中：</span><span class="sxs-lookup"><span data-stu-id="edfbd-128">For COM Add-ins installed for use by every user of the client computer, the registry key is located in the HKLM registry hive:</span></span>
  
`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\InfoPath\AddIns\`
  
<span data-ttu-id="edfbd-129">注册表项名称对应于**ProgIdAttribute**的外接程序，并包含以下值。</span><span class="sxs-lookup"><span data-stu-id="edfbd-129">The registry key name corresponds to the **ProgIdAttribute** of the add-in, and contains the following values.</span></span> 
  
|<span data-ttu-id="edfbd-130">**名称**</span><span class="sxs-lookup"><span data-stu-id="edfbd-130">**Name**</span></span>|<span data-ttu-id="edfbd-131">**类型**</span><span class="sxs-lookup"><span data-stu-id="edfbd-131">**Type**</span></span>|<span data-ttu-id="edfbd-132">**说明**</span><span class="sxs-lookup"><span data-stu-id="edfbd-132">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="edfbd-133">**FriendlyName**</span><span class="sxs-lookup"><span data-stu-id="edfbd-133">**FriendlyName**</span></span> <br/> |<span data-ttu-id="edfbd-134">**字符串**</span><span class="sxs-lookup"><span data-stu-id="edfbd-134">**String**</span></span> <br/> |<span data-ttu-id="edfbd-135">显示在**COM 加载项**对话框和**加载项**页上的**信任中心**中列出的名称。</span><span class="sxs-lookup"><span data-stu-id="edfbd-135">The name that is displayed in the **COM Add-ins** dialog box and listed in the **Add-ins** page of the **Trust Center**.</span></span>  <br/> |
|<span data-ttu-id="edfbd-136">**说明**</span><span class="sxs-lookup"><span data-stu-id="edfbd-136">**Description**</span></span> <br/> |<span data-ttu-id="edfbd-137">**字符串**</span><span class="sxs-lookup"><span data-stu-id="edfbd-137">**String**</span></span> <br/> |<span data-ttu-id="edfbd-138">**信任中心**中所选加载项时显示的字符串。</span><span class="sxs-lookup"><span data-stu-id="edfbd-138">The string that is displayed when the add-in is selected in the **Trust Center**.</span></span>  <br/> |
|<span data-ttu-id="edfbd-139">**LoadBehavior**</span><span class="sxs-lookup"><span data-stu-id="edfbd-139">**LoadBehavior**</span></span> <br/> |<span data-ttu-id="edfbd-140">**DWORD**</span><span class="sxs-lookup"><span data-stu-id="edfbd-140">**DWORD**</span></span> <br/> |<span data-ttu-id="edfbd-141">指定 COM 加载项已加载的方式。</span><span class="sxs-lookup"><span data-stu-id="edfbd-141">Specifies the way the COM Add-in is loaded.</span></span> <span data-ttu-id="edfbd-142">值可以是 0、 1、 2、 8 和 16 的组合。</span><span class="sxs-lookup"><span data-stu-id="edfbd-142">The value can be a combination of 0, 1, 2, 8, and 16.</span></span> <span data-ttu-id="edfbd-143">请参阅下表的详细信息。</span><span class="sxs-lookup"><span data-stu-id="edfbd-143">See the table below for more information.</span></span>  <br/> |
   
<span data-ttu-id="edfbd-144">**LoadBehavior**的**DWORD**值应包含一个描述如何 COM 加载项加载在编辑环境中的值。</span><span class="sxs-lookup"><span data-stu-id="edfbd-144">The **DWORD** value for **LoadBehavior** should contain a value describing how the COM Add-in loads in the editing environment.</span></span> <span data-ttu-id="edfbd-145">值可以是从下，表或表中的值的组合。</span><span class="sxs-lookup"><span data-stu-id="edfbd-145">The value can be from the table below, or a combination of values from the table.</span></span> <span data-ttu-id="edfbd-146">例如，COM 加载项创建 Visual Studio 2005 中将在应用程序启动具有"3"加载**LoadBehavior**和连接。</span><span class="sxs-lookup"><span data-stu-id="edfbd-146">For example, a COM Add-in created in Visual Studio 2005 will have a **LoadBehavior** of "3" loaded at application startup and be connected.</span></span> 
  
|<span data-ttu-id="edfbd-147">**值**</span><span class="sxs-lookup"><span data-stu-id="edfbd-147">**Value**</span></span>|<span data-ttu-id="edfbd-148">**说明**</span><span class="sxs-lookup"><span data-stu-id="edfbd-148">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="edfbd-149">0</span><span class="sxs-lookup"><span data-stu-id="edfbd-149">0</span></span>  <br/> |<span data-ttu-id="edfbd-150">断开连接。</span><span class="sxs-lookup"><span data-stu-id="edfbd-150">Disconnected.</span></span> <span data-ttu-id="edfbd-151">外接程序显示作为**COM 加载项**对话框中的非活动。</span><span class="sxs-lookup"><span data-stu-id="edfbd-151">The add-in shows as Inactive in the **COM Add-in** dialog box.</span></span>  <br/> |
|<span data-ttu-id="edfbd-152">1</span><span class="sxs-lookup"><span data-stu-id="edfbd-152">1</span></span>  <br/> |<span data-ttu-id="edfbd-153">连接。</span><span class="sxs-lookup"><span data-stu-id="edfbd-153">Connected.</span></span> <span data-ttu-id="edfbd-154">外接程序显示为**COM 加载项**对话框中的活动。</span><span class="sxs-lookup"><span data-stu-id="edfbd-154">The add-in shows as Active in the **COM Add-in** dialog box.</span></span>  <br/> |
|<span data-ttu-id="edfbd-155">2</span><span class="sxs-lookup"><span data-stu-id="edfbd-155">2</span></span>  <br/> |<span data-ttu-id="edfbd-156">在启动时加载。</span><span class="sxs-lookup"><span data-stu-id="edfbd-156">Load at Startup.</span></span> <span data-ttu-id="edfbd-157">加载项已加载并连接主机应用程序启动时。</span><span class="sxs-lookup"><span data-stu-id="edfbd-157">The add-in is loaded and connected when the host application starts.</span></span>  <br/> |
|<span data-ttu-id="edfbd-158">8</span><span class="sxs-lookup"><span data-stu-id="edfbd-158">8</span></span>  <br/> |<span data-ttu-id="edfbd-159">按需加载。</span><span class="sxs-lookup"><span data-stu-id="edfbd-159">Load on Demand.</span></span> <span data-ttu-id="edfbd-160">加载项已加载并连接时主机应用程序需要它，例如，当用户单击按钮用外接程序中的功能。</span><span class="sxs-lookup"><span data-stu-id="edfbd-160">The add-in is loaded and connected when the host application requires it, for example when a user clicks a button that uses functionality in the add-in.</span></span>  <br/> |
|<span data-ttu-id="edfbd-161">16</span><span class="sxs-lookup"><span data-stu-id="edfbd-161">16</span></span>  <br/> |<span data-ttu-id="edfbd-162">连接第一次。</span><span class="sxs-lookup"><span data-stu-id="edfbd-162">Connect first time.</span></span> <span data-ttu-id="edfbd-163">外接程序将加载和连接第一次用户运行外接程序注册后的主机应用程序。</span><span class="sxs-lookup"><span data-stu-id="edfbd-163">The add-in will be loaded and connected the first time the user runs the host application after registering the add-in.</span></span>  <br/> |
   
## <a name="creating-a-managed-com-add-in-with-visual-studio-2005-or-visual-studio-2008"></a><span data-ttu-id="edfbd-164">使用 Visual Studio 2005 或 Visual Studio 2008 创建托管的 COM 加载项</span><span class="sxs-lookup"><span data-stu-id="edfbd-164">Creating a Managed COM Add-in with Visual Studio 2005 or Visual Studio 2008</span></span>

<span data-ttu-id="edfbd-165">若要创建托管的 COM 加载项程序使用 Microsoft Visual Studio 2005 或 Visual Studio 2008、 创建共享的加载项项目，如下所示：</span><span class="sxs-lookup"><span data-stu-id="edfbd-165">To create a managed COM add-in using Microsoft Visual Studio 2005 or Visual Studio 2008, create a Shared Add-In project as follows:</span></span> 
  
1. <span data-ttu-id="edfbd-166">启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="edfbd-166">Start Visual Studio.</span></span>
    
2. <span data-ttu-id="edfbd-167">在“文件”**** 菜单上，单击“新建项目”****。</span><span class="sxs-lookup"><span data-stu-id="edfbd-167">On the **File** menu, click **New Project**.</span></span>
    
3. <span data-ttu-id="edfbd-168">在**新建项目**对话框的**项目类型**窗格中，单击**其他项目类型**文件夹，然后单击**扩展性**。</span><span class="sxs-lookup"><span data-stu-id="edfbd-168">In the **Project Types** pane of the **New Project** dialog box, click the **Other Projects Types** folder, and then click **Extensibility**.</span></span>
    
4. <span data-ttu-id="edfbd-169">在**模板**窗格中，单击**共享外接程序**。</span><span class="sxs-lookup"><span data-stu-id="edfbd-169">In the **Templates** pane, click **Shared Add-In**.</span></span>
    
5. <span data-ttu-id="edfbd-170">在**名称**框中，键入项目的名称。</span><span class="sxs-lookup"><span data-stu-id="edfbd-170">In the **Name** box, type a name for the project.</span></span> 
    
6. <span data-ttu-id="edfbd-171">在**位置**框中，键入文件夹路径或单击**浏览**选择文件夹路径，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="edfbd-171">In the **Location** box, type a folder path or click **Browse** and select a folder path, and then click **OK**.</span></span> <span data-ttu-id="edfbd-172">将显示**共享外接程序向导**。</span><span class="sxs-lookup"><span data-stu-id="edfbd-172">The **Shared Add-in Wizard** appears.</span></span> 
    
7. <span data-ttu-id="edfbd-173">单击**下一步**中**共享外接程序向导**。</span><span class="sxs-lookup"><span data-stu-id="edfbd-173">Click **Next** in the **Shared Add-in Wizard**.</span></span> <span data-ttu-id="edfbd-174">将出现**选择编程语言**页。</span><span class="sxs-lookup"><span data-stu-id="edfbd-174">The **Select a Programming Language** page appears.</span></span> 
    
8. <span data-ttu-id="edfbd-175">单击**使用 Visual Basic 加载项的创建**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="edfbd-175">Click **Create an Add-in using Visual Basic**, then click **Next**.</span></span> <span data-ttu-id="edfbd-176">将显示**选择应用程序主机**页。</span><span class="sxs-lookup"><span data-stu-id="edfbd-176">The **Select An Application Host** page appears.</span></span> 
    
9. <span data-ttu-id="edfbd-177">取消选中除**Microsoft InfoPath**，每个应用程序旁边的框，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="edfbd-177">Uncheck the boxes next to each application except **Microsoft InfoPath**, and then click **Next**.</span></span> <span data-ttu-id="edfbd-178">将显示**输入名称和说明**页。</span><span class="sxs-lookup"><span data-stu-id="edfbd-178">The **Enter a Name and Description** page appears.</span></span> 
    
10. <span data-ttu-id="edfbd-179">在**什么是外接程序的名称**框中，键入的 COM 加载项的名称。</span><span class="sxs-lookup"><span data-stu-id="edfbd-179">In the **What is the name of your Add-In** box, type the name of your COM Add-in.</span></span> 
    
11. <span data-ttu-id="edfbd-180">在**什么是外接程序的说明**框中，键入 COM 加载项的说明，，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="edfbd-180">In the **What is the description of your Add-In** box, type the description for your COM Add-in, and click **Next**.</span></span> <span data-ttu-id="edfbd-181">将出现**选择外接程序选项**页。</span><span class="sxs-lookup"><span data-stu-id="edfbd-181">The **Choose Add-In Options** page appears.</span></span> 
    
12. <span data-ttu-id="edfbd-182">选中**我希望我的外接程序时加载主机应用程序加载**和**我的加载项应为可供安装在不只是用户安装此人的计算机的所有用户**框。</span><span class="sxs-lookup"><span data-stu-id="edfbd-182">Check the **I would like my Add-in to load when the host application loads** and **My Add-in should be available to all users of the computer it was installed on, not just the person who installs it** boxes.</span></span> 
    
13. <span data-ttu-id="edfbd-183">单击**下一步**以查看**摘要**页中，然后单击**完成时间**。</span><span class="sxs-lookup"><span data-stu-id="edfbd-183">Click **Next** to review the **Summary** page, then click **Finish**.</span></span>
    
<span data-ttu-id="edfbd-184">Visual studio 创建项目后，您将看到解决方案资源管理器窗口中的两个项目。</span><span class="sxs-lookup"><span data-stu-id="edfbd-184">After the project is created by Visual Studio, you will see two projects in the Solution Explorer window.</span></span> <span data-ttu-id="edfbd-185">第一个项目是的 COM 加载项; 项目第二个项目是用于部署 COM 加载项的安装程序项目。</span><span class="sxs-lookup"><span data-stu-id="edfbd-185">The first project is the project for the COM Add-in; the second project is a setup project for deploying the COM Add-in.</span></span> <span data-ttu-id="edfbd-186">**共享外接程序向导**仅插入对**Microsoft Office 14.0 对象库**的引用，因此必须要插入到使用以下步骤 InfoPath 对象库的引用：</span><span class="sxs-lookup"><span data-stu-id="edfbd-186">The **Shared Add-in Wizard** only inserts a reference to the **Microsoft Office 14.0 Object Library**, so it is necessary to insert a reference to the InfoPath object library using the following steps:</span></span>
  
1. <span data-ttu-id="edfbd-187">双击**我的项目**显示外接程序项目属性。</span><span class="sxs-lookup"><span data-stu-id="edfbd-187">Double-click **My Project** to display the add-in project properties.</span></span> <span data-ttu-id="edfbd-188">单击**引用**选项卡以显示自动添加到项目的引用。</span><span class="sxs-lookup"><span data-stu-id="edfbd-188">Click the **References** tab to display the references automatically added to the project.</span></span> 
    
2. <span data-ttu-id="edfbd-189">单击**添加**按钮以显示**添加引用**对话框。</span><span class="sxs-lookup"><span data-stu-id="edfbd-189">Click the **Add** button to display the **Add Reference** dialog box.</span></span> 
    
3. <span data-ttu-id="edfbd-190">在**COM**选项卡上，双击**Microsoft.InfoPath 2.0 类型库**，并单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="edfbd-190">On the **COM** tab, double-click **Microsoft.InfoPath 2.0 Type Library**, and click **OK**.</span></span>
    
4. <span data-ttu-id="edfbd-191">添加对**Microsoft InfoPath 3.0 类型库**的引用也将引用添加到三个程序集，则必须删除： **ADODB**、 **MSHTML**和**MSXML2**。</span><span class="sxs-lookup"><span data-stu-id="edfbd-191">Adding a reference to the **Microsoft InfoPath 3.0 Type Library** also adds references to three assemblies that must be removed: **ADODB**, **MSHTML**, and **MSXML2**.</span></span> <span data-ttu-id="edfbd-192">在**引用**下的**解决方案资源管理器**中，右键单击其中每个引用，，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="edfbd-192">In **Solution Explorer** under **References**, right-click each of these references, and then click **Remove**.</span></span>
    
## <a name="viewing-the-registry-settings"></a><span data-ttu-id="edfbd-193">查看的注册表设置</span><span class="sxs-lookup"><span data-stu-id="edfbd-193">Viewing the Registry Settings</span></span>

<span data-ttu-id="edfbd-194">若要查看安装 COM 加载项时将创建的注册表设置，请按照下列步骤：</span><span class="sxs-lookup"><span data-stu-id="edfbd-194">To view the registry settings that will be created when the COM Add-in is installed, follow these steps:</span></span>
  
1. <span data-ttu-id="edfbd-195">右键单击安装项目在**解决方案资源管理器**中的根节点，单击**视图**，然后为**编辑器**，然后单击**注册表**。</span><span class="sxs-lookup"><span data-stu-id="edfbd-195">Right-click the root node of the setup project in the **Solution Explorer**, click **View**, then **Editor**, then click **Registry**.</span></span>
    
2. <span data-ttu-id="edfbd-196">在左侧窗格中，单击加号以展开**HKEY_LOCAL_MACHINE**、**软件**、 **Microsoft**、 **InfoPath**，然后**加载项**。</span><span class="sxs-lookup"><span data-stu-id="edfbd-196">In the left-hand pane, click the plus to expand **HKEY_LOCAL_MACHINE**, **Software**, **Microsoft**, **InfoPath**, then **AddIns**.</span></span>
    
3. <span data-ttu-id="edfbd-197">单击共享外接程序项目的**ProgID**与对应的名称。</span><span class="sxs-lookup"><span data-stu-id="edfbd-197">Click the name corresponding to your shared add-in project's **ProgID**.</span></span>
    
<span data-ttu-id="edfbd-198">若要更改其中的任何属性，右键单击该属性，单击**属性窗口**中，更改**属性窗口**中的**值**框。</span><span class="sxs-lookup"><span data-stu-id="edfbd-198">To change any of these properties, right-click the property, click **Properties Window**, and change the **Value** box in the **Properties Window**.</span></span>
  
## <a name="compiling-and-distributing-the-shared-add-in"></a><span data-ttu-id="edfbd-199">编译和分发共享的加载项</span><span class="sxs-lookup"><span data-stu-id="edfbd-199">Compiling and Distributing the Shared Add-In</span></span>

<span data-ttu-id="edfbd-200">若要用于测试开发了共享加载项项目的计算机上编译托管 COM 加载项，右键单击解决方案资源管理器中的共享外接程序项目的根节点，然后单击生成。</span><span class="sxs-lookup"><span data-stu-id="edfbd-200">To compile the managed COM Add-in for testing on the computer on which the Shared Add-In project was developed, right-click the root node of the Shared Add-In project in the Solution Explorer and click Build.</span></span> <span data-ttu-id="edfbd-201">如果将生成项目，并且没有错误，您可以启动 InfoPath 编辑环境并开始使用托管 COM 加载项。</span><span class="sxs-lookup"><span data-stu-id="edfbd-201">If the project builds with no errors, you can start the InfoPath editing environment and begin using the managed COM Add-in.</span></span> <span data-ttu-id="edfbd-202">如果您有运行的 InfoPath 实例，它构建项目之前将其关闭。</span><span class="sxs-lookup"><span data-stu-id="edfbd-202">If you have an instance of InfoPath running, close it before building the project.</span></span> <span data-ttu-id="edfbd-203">可能还需要打开 COM 加载项对话框中，若要验证 COM 加载项已注册。</span><span class="sxs-lookup"><span data-stu-id="edfbd-203">It may also be necessary to open the COM Add-ins dialog box to verify that the COM Add-in is registered.</span></span> <span data-ttu-id="edfbd-204">要打开 COM 加载项对话框，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="edfbd-204">To open the COM Add-ins dialog box, follow these steps:</span></span>
  
1. <span data-ttu-id="edfbd-205">打开 InfoPath 编辑环境。</span><span class="sxs-lookup"><span data-stu-id="edfbd-205">Open the InfoPath editing environment.</span></span> <span data-ttu-id="edfbd-206">执行此操作的最简单方法是打开现有的表单模板，将创建基于该表单模板的新表单。</span><span class="sxs-lookup"><span data-stu-id="edfbd-206">The easiest way to do this is to open an existing form template, which will create a new form based on that form template.</span></span>
    
2. <span data-ttu-id="edfbd-207">在**工具**菜单上，单击**信任中心**。</span><span class="sxs-lookup"><span data-stu-id="edfbd-207">Click **Trust Center** on the **Tools** menu.</span></span> 
    
3. <span data-ttu-id="edfbd-208">单击左侧的**加载项**类别。</span><span class="sxs-lookup"><span data-stu-id="edfbd-208">Click the **Add-ins** category on the left.</span></span> 
    
4. <span data-ttu-id="edfbd-209">在**信任中心**对话框的底部附近的**管理**部分中，从列表中选择**COM 加载项**，然后单击**转**按钮。</span><span class="sxs-lookup"><span data-stu-id="edfbd-209">In the **Manage** section near the bottom of the **Trust Center** dialog box, select **COM Add-ins** from the list and click the **Go** button.</span></span> 
    
5. <span data-ttu-id="edfbd-210">在**COM 加载项**对话框，您将看到您最近生成加载项的名称和应该有一个它旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="edfbd-210">In the **COM Add-ins** dialog box, you will see the name of your recently-built add-in and there should be a check box next to it.</span></span> <span data-ttu-id="edfbd-211">如果没有它旁边的复选框，COM 加载项无法加载由于错误，将在对话框中的**加载行为**部分中列出。</span><span class="sxs-lookup"><span data-stu-id="edfbd-211">If there is no check box next to it, the COM Add-in failed to load due to an error, which will be listed in the **Load Behavior** section of the dialog box.</span></span> 
    
<span data-ttu-id="edfbd-212">编译托管 COM 加载项用于共享的加载项项目开发所在计算机以外的计算机上，您必须执行额外的步骤来保护您的代码。</span><span class="sxs-lookup"><span data-stu-id="edfbd-212">To compile the managed COM add-in for use on a computer other than the computer on which the Shared Add-In project was developed, you must follow additional steps to secure your code.</span></span> <span data-ttu-id="edfbd-213">保护共享加载项项目的其他计算机上使用的信息，请参阅下面的三篇文章：</span><span class="sxs-lookup"><span data-stu-id="edfbd-213">For information on securing Shared Add-In projects for use on other computers, see the following three articles:</span></span>
  
- [<span data-ttu-id="edfbd-214">部署的托管 COM 加载项中 Office XP</span><span class="sxs-lookup"><span data-stu-id="edfbd-214">Deployment of Managed COM Add-Ins in Office XP</span></span>](http://go.microsoft.com/fwlink/?LinkID=73473)
  
- [<span data-ttu-id="edfbd-215">使用 COM 加载项填充码解决方案部署托管 COM 加载项中 Office XP</span><span class="sxs-lookup"><span data-stu-id="edfbd-215">Using the COM Add-in Shim Solution to Deploy Managed COM Add-ins in Office XP</span></span>](http://go.microsoft.com/fwlink/?LinkID=73474)
  
- [<span data-ttu-id="edfbd-216">隔离 Office 扩展 COM 填充码向导</span><span class="sxs-lookup"><span data-stu-id="edfbd-216">Isolating Office Extensions with the COM Shim Wizard</span></span>](http://go.microsoft.com/fwlink/?LinkID=73475)
  
> [!IMPORTANT]
> <span data-ttu-id="edfbd-217">如果不隔离 COM 加载项可能会导致内存泄漏和应用程序不稳定。</span><span class="sxs-lookup"><span data-stu-id="edfbd-217">Not isolating the COM Add-in may cause memory leaks and application instability.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="edfbd-218">.NET Framework 或其他所需的程序集从安装项目尚未安装在目标计算机上，如果.msi 文件可能无法正确安装。</span><span class="sxs-lookup"><span data-stu-id="edfbd-218">If the .NET Framework or other required assemblies from the setup project are not already installed on target computers, the .msi file may not install properly.</span></span> <span data-ttu-id="edfbd-219">此外，您不能分发的.msi 文件，然后尝试安装该.msi 文件。</span><span class="sxs-lookup"><span data-stu-id="edfbd-219">Also, you cannot distribute the .msi file and then attempt to install the .msi file.</span></span> <span data-ttu-id="edfbd-220">您还必须分发 Visual Studio 生成的原始.msi 文件所在的文件夹中的其他支持文件。</span><span class="sxs-lookup"><span data-stu-id="edfbd-220">You must also distribute the other support files in the same folder as the original .msi file generated by Visual Studio.</span></span> 
  
## <a name="coding-in-the-com-add-in"></a><span data-ttu-id="edfbd-221">编码的 COM 加载项</span><span class="sxs-lookup"><span data-stu-id="edfbd-221">Coding in the COM Add-in</span></span>

<span data-ttu-id="edfbd-222">InfoPath 表单编辑环境中发生的事件，可以捕获由 COM 加载项。</span><span class="sxs-lookup"><span data-stu-id="edfbd-222">Application events that occur in the InfoPath form editing environment can be captured by a COM Add-in.</span></span> <span data-ttu-id="edfbd-223">[ApplicationEvents](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.ApplicationEvents.aspx)对象的以下事件可由 COM 加载项，用于响应用户操作：</span><span class="sxs-lookup"><span data-stu-id="edfbd-223">The following events of the [ApplicationEvents](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.ApplicationEvents.aspx) object can be used by the COM Add-in to respond to user actions:</span></span> 
  
|<span data-ttu-id="edfbd-224">"事件"</span><span class="sxs-lookup"><span data-stu-id="edfbd-224">**Event**</span></span>|<span data-ttu-id="edfbd-225">**说明**</span><span class="sxs-lookup"><span data-stu-id="edfbd-225">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="edfbd-226">[NewXDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.NewXDocument.aspx)事件</span><span class="sxs-lookup"><span data-stu-id="edfbd-226">[NewXDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.NewXDocument.aspx) Event</span></span>  <br/> |<span data-ttu-id="edfbd-227">新建表单时发生。</span><span class="sxs-lookup"><span data-stu-id="edfbd-227">Occurs when a new form is created.</span></span>  <br/> |
|<span data-ttu-id="edfbd-228">[退出](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.Quit.aspx)事件</span><span class="sxs-lookup"><span data-stu-id="edfbd-228">[Quit](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.Quit.aspx) Event</span></span>  <br/> |<span data-ttu-id="edfbd-229">用户退出 InfoPath 时发生。</span><span class="sxs-lookup"><span data-stu-id="edfbd-229">Occurs when the user quits InfoPath.</span></span>  <br/> |
|<span data-ttu-id="edfbd-230">[WindowActivate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.WindowActivate.aspx)事件</span><span class="sxs-lookup"><span data-stu-id="edfbd-230">[WindowActivate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.WindowActivate.aspx) Event</span></span>  <br/> |<span data-ttu-id="edfbd-231">在激活文档窗口时发生。</span><span class="sxs-lookup"><span data-stu-id="edfbd-231">Occurs when any document window is activated.</span></span>  <br/> |
|<span data-ttu-id="edfbd-232">[WindowDeactivate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.WindowDeactivate.aspx)事件</span><span class="sxs-lookup"><span data-stu-id="edfbd-232">[WindowDeactivate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.WindowDeactivate.aspx) Event</span></span>  <br/> |<span data-ttu-id="edfbd-233">在文档窗口成为非活动窗口时发生。</span><span class="sxs-lookup"><span data-stu-id="edfbd-233">Occurs when any document window is deactivated.</span></span>  <br/> |
|<span data-ttu-id="edfbd-234">[WindowSize](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.WindowSize.aspx)事件</span><span class="sxs-lookup"><span data-stu-id="edfbd-234">[WindowSize](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.WindowSize.aspx) Event</span></span>  <br/> |<span data-ttu-id="edfbd-235">当调整任一文档窗口大小或移动该窗口时发生。</span><span class="sxs-lookup"><span data-stu-id="edfbd-235">Occurs when any document window is resized or moved.</span></span>  <br/> |
|<span data-ttu-id="edfbd-236">[XDocumentBeforeClose](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentBeforeClose.aspx)事件</span><span class="sxs-lookup"><span data-stu-id="edfbd-236">[XDocumentBeforeClose](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentBeforeClose.aspx) Event</span></span>  <br/> |<span data-ttu-id="edfbd-237">在打开的文档即将关闭之前发生。</span><span class="sxs-lookup"><span data-stu-id="edfbd-237">Occurs immediately before any open document closes.</span></span>  <br/> |
|<span data-ttu-id="edfbd-238">[XDocumentBeforePrint](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentBeforePrint.aspx)事件</span><span class="sxs-lookup"><span data-stu-id="edfbd-238">[XDocumentBeforePrint](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentBeforePrint.aspx) Event</span></span>  <br/> |<span data-ttu-id="edfbd-239">在即将打印任一打开文档时发生。</span><span class="sxs-lookup"><span data-stu-id="edfbd-239">Occurs immediately before any open document is printed.</span></span>  <br/> |
|<span data-ttu-id="edfbd-240">[XDocumentBeforeSave](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentBeforeSave.aspx)事件</span><span class="sxs-lookup"><span data-stu-id="edfbd-240">[XDocumentBeforeSave](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentBeforeSave.aspx) Event</span></span>  <br/> |<span data-ttu-id="edfbd-241">在即将保存任一打开文档时发生。</span><span class="sxs-lookup"><span data-stu-id="edfbd-241">Occurs immediately before any open document is saved.</span></span>  <br/> |
|<span data-ttu-id="edfbd-242">[XDocumentChange](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentChange.aspx)事件</span><span class="sxs-lookup"><span data-stu-id="edfbd-242">[XDocumentChange](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentChange.aspx) Event</span></span>  <br/> |<span data-ttu-id="edfbd-243">新建表单、打开现有表单或另一个表单变为激活状态时发生。</span><span class="sxs-lookup"><span data-stu-id="edfbd-243">Occurs when a new form is created, when an existing form is opened, or when another form is made the active form.</span></span>  <br/> |
|<span data-ttu-id="edfbd-244">[XDocumentOpen](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentOpen.aspx)事件</span><span class="sxs-lookup"><span data-stu-id="edfbd-244">[XDocumentOpen](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentOpen.aspx) Event</span></span>  <br/> |<span data-ttu-id="edfbd-245">在打开文档时发生。</span><span class="sxs-lookup"><span data-stu-id="edfbd-245">Occurs when a document is opened.</span></span>  <br/> |
   
<span data-ttu-id="edfbd-246">要捕获 COM 加载项中的这些事件，您必须在**Connect**类中声明的以下类级变量：</span><span class="sxs-lookup"><span data-stu-id="edfbd-246">To capture these events in the COM Add-in, you must declare the following class-level variables in your **Connect** class:</span></span> 
  
```vb
InfoPathApplication = DirectCast( _
   application, Microsoft.Office.Interop.InfoPath._Application3)
InfoPathApplicationEvents = DirectCast( _
   InfoPathApplication.Events, _
   Microsoft.Office.Interop.InfoPath.ApplicationEvents)
```

```cs
InfoPathApplication =
   (Microsoft.Office.Interop.InfoPath._Application3)application;
InfoPathApplicationEvents =
   (Microsoft.Office.Interop.InfoPath.ApplicationEvents)
   InfoPathApplication.Events;
```

<span data-ttu-id="edfbd-247">第一行投射**对象**接收的外接程序对[_Application3](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._Application3.aspx)对象的常规应用程序。</span><span class="sxs-lookup"><span data-stu-id="edfbd-247">The first line casts the generic application **Object** received by the add-in to the [_Application3](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._Application3.aspx) object.</span></span> <span data-ttu-id="edfbd-248">第二行将 （由**InfoPathApplication**变量） **_Application3**对象的[事件](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._Application3.Events.aspx)属性强制转换为[ApplicationEvents](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.ApplicationEvents.aspx)对象。</span><span class="sxs-lookup"><span data-stu-id="edfbd-248">The second line casts the [Events](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._Application3.Events.aspx) property of the **_Application3** object (represented by the **InfoPathApplication** variable) to the [ApplicationEvents](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.ApplicationEvents.aspx) object.</span></span> 
  
<span data-ttu-id="edfbd-249">要创建事件处理程序，请从**类名**下拉列表框顶部的 Visual Studio 窗口中，选择**InfoPathApplicationEvents** ，然后选择您想要在可视顶部的**方法名称**下拉列表框中处理的事件Studio 窗口。</span><span class="sxs-lookup"><span data-stu-id="edfbd-249">To create event handlers, select **InfoPathApplicationEvents** from the **Class Name** drop-down box at the top of the Visual Studio window, and then select the event you want to handle in the **Method Name** drop-down box at the top of the Visual Studio window.</span></span> <span data-ttu-id="edfbd-250">例如，如果您需要控制保存表单时，您可以处理**XDocumentBeforeSave**事件。</span><span class="sxs-lookup"><span data-stu-id="edfbd-250">For example, if you need to control when a form is saved, you handle the **XDocumentBeforeSave** event.</span></span> <span data-ttu-id="edfbd-251">自动从**方法名称**下拉列表中选择**XDocumentBeforeSave**插入下面的过程：</span><span class="sxs-lookup"><span data-stu-id="edfbd-251">Selecting **XDocumentBeforeSave** from the **Method Name** drop-down automatically inserts the following procedure:</span></span> 
  
```vb
Private Sub InfoPathApplicationEvents_XDocumentBeforeSave( _
   ByVal pDocument As Microsoft.Office.Interop.InfoPath._XDocument, _
   ByRef pfCancel As Boolean) _
   Handles InfoPathApplicationEvents.XDocumentBeforeSave
End Sub
```

```cs
private void InfoPathApplicationEvents_XDocumentBeforeSave(
   Microsoft.Office.Interop.InfoPath._XDocument pDocument, ref bool pfCancel)
{
}

```

<span data-ttu-id="edfbd-252">任一**ApplicationEvents**对象的事件可以处理由 COM 加载项使用相同的方法。</span><span class="sxs-lookup"><span data-stu-id="edfbd-252">Any of the events of the **ApplicationEvents** object can be handled by the COM Add-in using the same method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="edfbd-253">另请参阅</span><span class="sxs-lookup"><span data-stu-id="edfbd-253">See also</span></span>

- [<span data-ttu-id="edfbd-254">创建 Microsoft Office 2000 COM 加载项</span><span class="sxs-lookup"><span data-stu-id="edfbd-254">Creating a Microsoft Office 2000 COM Add-in</span></span>](http://go.microsoft.com/fwlink/?LinkID=73468) 
- [<span data-ttu-id="edfbd-255">创建 Office 托管 COM 加载项使用 Visual Studio.NET</span><span class="sxs-lookup"><span data-stu-id="edfbd-255">Creating Office Managed COM Add-Ins with Visual Studio .NET</span></span>](http://go.microsoft.com/fwlink/?LinkID=73470)
- [<span data-ttu-id="edfbd-256">使用 IDTExtensibility2 事件过程</span><span class="sxs-lookup"><span data-stu-id="edfbd-256">Working with the IDTExtensibility2 Event Procedures</span></span>](http://go.microsoft.com/fwlink/?LinkID=73471)
- [<span data-ttu-id="edfbd-257">构建 Office COM 加载项与 Visual Basic.NET</span><span class="sxs-lookup"><span data-stu-id="edfbd-257">Build an Office COM Add-in With Visual Basic .NET</span></span>](http://go.microsoft.com/fwlink/?LinkID=73469)
- [<span data-ttu-id="edfbd-258">构建 Office COM 加载项使用 Visual C#.NET</span><span class="sxs-lookup"><span data-stu-id="edfbd-258">Build an Office COM Add-in With Visual C# .NET</span></span>](http://go.microsoft.com/fwlink/?LinkID=73472)
- [<span data-ttu-id="edfbd-259">使用 Visual Studio 2005 Tools for the Office System SE 创建 InfoPath 2007 加载项</span><span class="sxs-lookup"><span data-stu-id="edfbd-259">Creating InfoPath 2007 Add-Ins by Using Visual Studio 2005 Tools for the Office System SE</span></span>](http://msdn.microsoft.com/en-us/library/bb968857%28office.12%29.aspx)

