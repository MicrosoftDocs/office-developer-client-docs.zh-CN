---
title: 创建 COM 加载项以将自定义功能添加到 InfoPath
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
keywords:
- infopath 2007， creating com add-ins，InfoPath 2007， adding custom features，COM add-ins [InfoPath 2007]
localization_priority: Normal
ms.assetid: af0b0bc9-20ef-4503-8b3b-8f2a97b671a2
description: 为了扩展表单编辑的用户体验，Microsoft InfoPath 支持 COM 加载项。 尽管首先在 InfoPath 中添加了对 COM 加载项的支持，但自 2000 Office 以来，其他 Office 应用程序（如 Microsoft Office Word 和 Microsoft Office Excel）也支持 COM 加载项。
ms.openlocfilehash: f8dd16b161c4ea862cf3b15e56e26a2547c1fc4c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303785"
---
# <a name="create-a-com-add-in-to-add-custom-features-to-infopath"></a><span data-ttu-id="d95dc-105">创建 COM 加载项以将自定义功能添加到 InfoPath</span><span class="sxs-lookup"><span data-stu-id="d95dc-105">Create a COM Add-in to Add Custom Features to InfoPath</span></span>

<span data-ttu-id="d95dc-106">为了扩展表单编辑的用户体验，Microsoft InfoPath 支持 COM 加载项。</span><span class="sxs-lookup"><span data-stu-id="d95dc-106">Microsoft InfoPath supports COM Add-ins for extending the form editing user experience.</span></span> <span data-ttu-id="d95dc-107">尽管首先在 InfoPath 中添加了对 COM 加载项的支持，但自 2000 Office 以来，其他 Office 应用程序（如 Microsoft Office Word 和 Microsoft Office Excel）也支持 COM 加载项。</span><span class="sxs-lookup"><span data-stu-id="d95dc-107">Although support for COM Add-ins was first added in InfoPath, other Office applications such as Microsoft Office Word and Microsoft Office Excel have supported COM add-ins since Office 2000.</span></span>
  
<span data-ttu-id="d95dc-108">InfoPath 中的 COM 加载项支持适用于表单编辑环境。</span><span class="sxs-lookup"><span data-stu-id="d95dc-108">COM Add-in support in InfoPath is available for the form editing environment.</span></span> <span data-ttu-id="d95dc-109">无法使用 COM 加载项扩展表单设计环境。</span><span class="sxs-lookup"><span data-stu-id="d95dc-109">The form design environment cannot be extended by using COM Add-ins.</span></span>
  
## <a name="the-idtextensibility2-interface"></a><span data-ttu-id="d95dc-110">IDTExtensibility2 接口</span><span class="sxs-lookup"><span data-stu-id="d95dc-110">The IDTExtensibility2 Interface</span></span>

<span data-ttu-id="d95dc-111">InfoPath 编辑环境支持 **IDTExtensibility2** 接口，该接口必须由 COM 加载项的开发人员实现。 **IDTExtensibility2** 是一个双接口对象，提供五个方法，这些方法在编辑环境中充当事件。</span><span class="sxs-lookup"><span data-stu-id="d95dc-111">The InfoPath editing environment provides support for the **IDTExtensibility2** interface, which must be implemented by developers of COM Add-ins. **IDTExtensibility2** is a dual-interface object that provides five methods which act as events within the editing environment.</span></span> <span data-ttu-id="d95dc-112">这些方法允许 COM 加载项响应环境启动和关闭条件，如下表所列。</span><span class="sxs-lookup"><span data-stu-id="d95dc-112">These methods allow the COM add-in to respond to environment startup and shutdown conditions, listed in the following table.</span></span> 
  
|<span data-ttu-id="d95dc-113">**接口**</span><span class="sxs-lookup"><span data-stu-id="d95dc-113">**Interface**</span></span>|<span data-ttu-id="d95dc-114">**说明**</span><span class="sxs-lookup"><span data-stu-id="d95dc-114">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d95dc-115">**OnAddInsUpdate (ByVal 自定义 () As Variant)**</span><span class="sxs-lookup"><span data-stu-id="d95dc-115">**OnAddInsUpdate (ByVal custom() As Variant)**</span></span> <br/> |<span data-ttu-id="d95dc-116">在环境中加载或卸载加载项时发生。</span><span class="sxs-lookup"><span data-stu-id="d95dc-116">Occurs when an add-in is loaded or unloaded in the environment.</span></span>  <br/> |
|<span data-ttu-id="d95dc-117">**OnBeginShutdown (ByVal 自定义 () 作为变量)**</span><span class="sxs-lookup"><span data-stu-id="d95dc-117">**OnBeginShutdown (ByVal custom() As Variant)**</span></span> <br/> |<span data-ttu-id="d95dc-118">在关闭环境时发生。</span><span class="sxs-lookup"><span data-stu-id="d95dc-118">Occurs when the environment is being shut down.</span></span>  <br/> |
|<span data-ttu-id="d95dc-119">**OnConnection (ByVal Application As Object， ByVal ConnectMode As ext_ConnectMode， ByVal AddInInst As Object， ByVal custom () As Variant)**</span><span class="sxs-lookup"><span data-stu-id="d95dc-119">**OnConnection(ByVal Application As Object, ByVal ConnectMode As ext_ConnectMode, ByVal AddInInst As Object, ByVal custom() As Variant)**</span></span> <br/> |<span data-ttu-id="d95dc-120">在环境中加载加载项时发生。</span><span class="sxs-lookup"><span data-stu-id="d95dc-120">Occurs when an add-in is loaded in the environment.</span></span>  <br/> |
|<span data-ttu-id="d95dc-121">**OnDisconnection (ByVal RemoveMode As ext_DisconnectMode， ByVal custom () As Variant)**</span><span class="sxs-lookup"><span data-stu-id="d95dc-121">**OnDisconnection (ByVal RemoveMode As ext_DisconnectMode, ByVal custom() As Variant)**</span></span> <br/> |<span data-ttu-id="d95dc-122">从环境中卸载外接程序时发生。</span><span class="sxs-lookup"><span data-stu-id="d95dc-122">Occurs when an add-in is unloaded from the environment.</span></span>  <br/> |
|<span data-ttu-id="d95dc-123">**OnStartupComplete (ByVal 自定义 () 作为变量)**</span><span class="sxs-lookup"><span data-stu-id="d95dc-123">**OnStartupComplete (ByVal custom() As Variant)**</span></span> <br/> |<span data-ttu-id="d95dc-124">在环境完成启动时发生。</span><span class="sxs-lookup"><span data-stu-id="d95dc-124">Occurs when the environment has completed starting.</span></span>  <br/> |
   
## <a name="registering-com-add-ins"></a><span data-ttu-id="d95dc-125">注册 COM 加载项</span><span class="sxs-lookup"><span data-stu-id="d95dc-125">Registering COM Add-ins</span></span>

<span data-ttu-id="d95dc-126">所有 Office 应用程序（包括 InfoPath）都使用注册表在 COM Add-Ins 集合中列出加载项，存储连接状态，并存储启动或需求加载信息。</span><span class="sxs-lookup"><span data-stu-id="d95dc-126">All Office applications, including InfoPath, use the registry to list add-ins in the COM Add-Ins collection, to store the connect state, and to store the boot or demand load information.</span></span> <span data-ttu-id="d95dc-127">对于 InfoPath COM 加载项，每个加载项的名称都显示在以下项下：</span><span class="sxs-lookup"><span data-stu-id="d95dc-127">For InfoPath COM Add-ins, the name of each add-in appears under the following key:</span></span>
  
`HKEY_CURRENT_USER\Software\Microsoft\Office\InfoPath\AddIns\`
  
<span data-ttu-id="d95dc-128">对于已安装供客户端计算机的每个用户使用的 COM 加载项，注册表项位于 HKLM 注册表配置单元中：</span><span class="sxs-lookup"><span data-stu-id="d95dc-128">For COM Add-ins installed for use by every user of the client computer, the registry key is located in the HKLM registry hive:</span></span>
  
`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\InfoPath\AddIns\`
  
<span data-ttu-id="d95dc-129">注册表项名称对应于加载项的 **ProgIdAttribute，** 并包含以下值。</span><span class="sxs-lookup"><span data-stu-id="d95dc-129">The registry key name corresponds to the **ProgIdAttribute** of the add-in, and contains the following values.</span></span> 
  
|<span data-ttu-id="d95dc-130">**名称**</span><span class="sxs-lookup"><span data-stu-id="d95dc-130">**Name**</span></span>|<span data-ttu-id="d95dc-131">**类型**</span><span class="sxs-lookup"><span data-stu-id="d95dc-131">**Type**</span></span>|<span data-ttu-id="d95dc-132">**说明**</span><span class="sxs-lookup"><span data-stu-id="d95dc-132">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d95dc-133">**FriendlyName**</span><span class="sxs-lookup"><span data-stu-id="d95dc-133">**FriendlyName**</span></span> <br/> |<span data-ttu-id="d95dc-134">**String**</span><span class="sxs-lookup"><span data-stu-id="d95dc-134">**String**</span></span> <br/> |<span data-ttu-id="d95dc-135">显示在 **"COM** 加载项"对话框中，并列在信任中心的"加载项"页 **中的名称**。 </span><span class="sxs-lookup"><span data-stu-id="d95dc-135">The name that is displayed in the **COM Add-ins** dialog box and listed in the **Add-ins** page of the **Trust Center**.</span></span>  <br/> |
|<span data-ttu-id="d95dc-136">**说明**</span><span class="sxs-lookup"><span data-stu-id="d95dc-136">**Description**</span></span> <br/> |<span data-ttu-id="d95dc-137">**字符串**</span><span class="sxs-lookup"><span data-stu-id="d95dc-137">**String**</span></span> <br/> |<span data-ttu-id="d95dc-138">在信任中心选择加载项时显示的 **字符串**。</span><span class="sxs-lookup"><span data-stu-id="d95dc-138">The string that is displayed when the add-in is selected in the **Trust Center**.</span></span>  <br/> |
|<span data-ttu-id="d95dc-139">**LoadBehavior**</span><span class="sxs-lookup"><span data-stu-id="d95dc-139">**LoadBehavior**</span></span> <br/> |<span data-ttu-id="d95dc-140">**DWORD**</span><span class="sxs-lookup"><span data-stu-id="d95dc-140">**DWORD**</span></span> <br/> |<span data-ttu-id="d95dc-141">指定加载 COM 加载项的方式。</span><span class="sxs-lookup"><span data-stu-id="d95dc-141">Specifies the way the COM Add-in is loaded.</span></span> <span data-ttu-id="d95dc-142">该值可以是 0、1、2、8 和 16 的组合。</span><span class="sxs-lookup"><span data-stu-id="d95dc-142">The value can be a combination of 0, 1, 2, 8, and 16.</span></span> <span data-ttu-id="d95dc-143">有关详细信息，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="d95dc-143">See the table below for more information.</span></span>  <br/> |
   
<span data-ttu-id="d95dc-144">**LoadBehavior** 的 **DWORD** 值应包含一个值，该值描述 COM 加载项在编辑环境中如何加载。</span><span class="sxs-lookup"><span data-stu-id="d95dc-144">The **DWORD** value for **LoadBehavior** should contain a value describing how the COM Add-in loads in the editing environment.</span></span> <span data-ttu-id="d95dc-145">该值可以是下表中的值，也可以来自该表的值的组合。</span><span class="sxs-lookup"><span data-stu-id="d95dc-145">The value can be from the table below, or a combination of values from the table.</span></span> <span data-ttu-id="d95dc-146">例如，在 Visual Studio 2005 中创建的 COM 加载项将在应用程序启动时加载 **LoadBehavior"3"** 并连接。</span><span class="sxs-lookup"><span data-stu-id="d95dc-146">For example, a COM Add-in created in Visual Studio 2005 will have a **LoadBehavior** of "3" loaded at application startup and be connected.</span></span> 
  
|<span data-ttu-id="d95dc-147">**值**</span><span class="sxs-lookup"><span data-stu-id="d95dc-147">**Value**</span></span>|<span data-ttu-id="d95dc-148">**说明**</span><span class="sxs-lookup"><span data-stu-id="d95dc-148">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d95dc-149">0</span><span class="sxs-lookup"><span data-stu-id="d95dc-149">0</span></span>  <br/> |<span data-ttu-id="d95dc-150">已断开连接。</span><span class="sxs-lookup"><span data-stu-id="d95dc-150">Disconnected.</span></span> <span data-ttu-id="d95dc-151">加载项在"COM 加载项"对话框中 **显示为"非活动** "。</span><span class="sxs-lookup"><span data-stu-id="d95dc-151">The add-in shows as Inactive in the **COM Add-in** dialog box.</span></span>  <br/> |
|<span data-ttu-id="d95dc-152">1</span><span class="sxs-lookup"><span data-stu-id="d95dc-152">1</span></span>  <br/> |<span data-ttu-id="d95dc-153">已连接。</span><span class="sxs-lookup"><span data-stu-id="d95dc-153">Connected.</span></span> <span data-ttu-id="d95dc-154">加载项在"COM 加载项"对话框中 **显示为"活动** "。</span><span class="sxs-lookup"><span data-stu-id="d95dc-154">The add-in shows as Active in the **COM Add-in** dialog box.</span></span>  <br/> |
|<span data-ttu-id="d95dc-155">2</span><span class="sxs-lookup"><span data-stu-id="d95dc-155">2</span></span>  <br/> |<span data-ttu-id="d95dc-156">启动时加载。</span><span class="sxs-lookup"><span data-stu-id="d95dc-156">Load at Startup.</span></span> <span data-ttu-id="d95dc-157">主机应用程序启动时加载并连接加载项。</span><span class="sxs-lookup"><span data-stu-id="d95dc-157">The add-in is loaded and connected when the host application starts.</span></span>  <br/> |
|<span data-ttu-id="d95dc-158">8 </span><span class="sxs-lookup"><span data-stu-id="d95dc-158">8</span></span>  <br/> |<span data-ttu-id="d95dc-159">按需加载。</span><span class="sxs-lookup"><span data-stu-id="d95dc-159">Load on Demand.</span></span> <span data-ttu-id="d95dc-160">当主机应用程序需要加载项时（例如，当用户单击使用加载项中的功能的按钮时）加载并连接加载项。</span><span class="sxs-lookup"><span data-stu-id="d95dc-160">The add-in is loaded and connected when the host application requires it, for example when a user clicks a button that uses functionality in the add-in.</span></span>  <br/> |
|<span data-ttu-id="d95dc-161">16 </span><span class="sxs-lookup"><span data-stu-id="d95dc-161">16</span></span>  <br/> |<span data-ttu-id="d95dc-162">第一次运行时连接。</span><span class="sxs-lookup"><span data-stu-id="d95dc-162">Connect first time.</span></span> <span data-ttu-id="d95dc-163">注册外接程序后，用户首次运行主机应用程序时，将加载并连接外接程序。</span><span class="sxs-lookup"><span data-stu-id="d95dc-163">The add-in will be loaded and connected the first time the user runs the host application after registering the add-in.</span></span>  <br/> |
   
## <a name="creating-a-managed-com-add-in-with-visual-studio-2005-or-visual-studio-2008"></a><span data-ttu-id="d95dc-164">使用 Visual Studio 2005 或 Visual Studio 2008 创建托管 COM 加载项</span><span class="sxs-lookup"><span data-stu-id="d95dc-164">Creating a Managed COM Add-in with Visual Studio 2005 or Visual Studio 2008</span></span>

<span data-ttu-id="d95dc-165">若要使用 Microsoft Visual Studio 2005 或 Visual Studio 2008 创建托管 COM Add-In项目，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d95dc-165">To create a managed COM add-in using Microsoft Visual Studio 2005 or Visual Studio 2008, create a Shared Add-In project as follows:</span></span> 
  
1. <span data-ttu-id="d95dc-166">启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="d95dc-166">Start Visual Studio.</span></span>
    
2. <span data-ttu-id="d95dc-167">在“文件”菜单上，单击“新建项目”。</span><span class="sxs-lookup"><span data-stu-id="d95dc-167">On the **File** menu, click **New Project**.</span></span>
    
3. <span data-ttu-id="d95dc-168">In the **Project Types** pane of the **New Project** dialog box， click the **Other Projects Types** folder， and then click **Extensibility**.</span><span class="sxs-lookup"><span data-stu-id="d95dc-168">In the **Project Types** pane of the **New Project** dialog box, click the **Other Projects Types** folder, and then click **Extensibility**.</span></span>
    
4. <span data-ttu-id="d95dc-169">在 **"模板"窗格中**，单击"**共享加载项"。**</span><span class="sxs-lookup"><span data-stu-id="d95dc-169">In the **Templates** pane, click **Shared Add-In**.</span></span>
    
5. <span data-ttu-id="d95dc-170">在 **"名称** "框中，键入项目的名称。</span><span class="sxs-lookup"><span data-stu-id="d95dc-170">In the **Name** box, type a name for the project.</span></span> 
    
6. <span data-ttu-id="d95dc-171">在"**位置"** 框中，键入文件夹路径 **或单击"** 浏览"并选择文件夹路径，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="d95dc-171">In the **Location** box, type a folder path or click **Browse** and select a folder path, and then click **OK**.</span></span> <span data-ttu-id="d95dc-172">将显示 **"共享外接程序向导** "。</span><span class="sxs-lookup"><span data-stu-id="d95dc-172">The **Shared Add-in Wizard** appears.</span></span> 
    
7. <span data-ttu-id="d95dc-173">单击 **共享** 加载项 **向导中的"下一步"。**</span><span class="sxs-lookup"><span data-stu-id="d95dc-173">Click **Next** in the **Shared Add-in Wizard**.</span></span> <span data-ttu-id="d95dc-174">将显示 **"选择编程语言"** 页。</span><span class="sxs-lookup"><span data-stu-id="d95dc-174">The **Select a Programming Language** page appears.</span></span> 
    
8. <span data-ttu-id="d95dc-175">单击 **"使用加载项创建Visual Basic"，** 然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="d95dc-175">Click **Create an Add-in using Visual Basic**, then click **Next**.</span></span> <span data-ttu-id="d95dc-176">将显示 **"选择应用程序主机"** 页。</span><span class="sxs-lookup"><span data-stu-id="d95dc-176">The **Select An Application Host** page appears.</span></span> 
    
9. <span data-ttu-id="d95dc-177">取消选中每个应用程序 **（Microsoft InfoPath** 除外）旁边的框，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="d95dc-177">Uncheck the boxes next to each application except **Microsoft InfoPath**, and then click **Next**.</span></span> <span data-ttu-id="d95dc-178">将显示 **"输入名称和说明"** 页。</span><span class="sxs-lookup"><span data-stu-id="d95dc-178">The **Enter a Name and Description** page appears.</span></span> 
    
10. <span data-ttu-id="d95dc-179">在 **"什么是加载项名称"框中** ，键入 COM 加载项的名称。</span><span class="sxs-lookup"><span data-stu-id="d95dc-179">In the **What is the name of your Add-In** box, type the name of your COM Add-in.</span></span> 
    
11. <span data-ttu-id="d95dc-180">在 **"什么是加载项** 说明"框中，键入 COM 加载项的说明，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="d95dc-180">In the **What is the description of your Add-In** box, type the description for your COM Add-in, and click **Next**.</span></span> <span data-ttu-id="d95dc-181">将显示 **"Add-In选项"** 页。</span><span class="sxs-lookup"><span data-stu-id="d95dc-181">The **Choose Add-In Options** page appears.</span></span> 
    
12. <span data-ttu-id="d95dc-182">选中 **"我希望在加载主机** 应用程序时加载我的外接程序"和"我的外接程序"应可供安装它的计算机的所有用户使用，而不只是将其安装在框中。</span><span class="sxs-lookup"><span data-stu-id="d95dc-182">Check the **I would like my Add-in to load when the host application loads** and **My Add-in should be available to all users of the computer it was installed on, not just the person who installs it** boxes.</span></span> 
    
13. <span data-ttu-id="d95dc-183">单击 **"下** 一步"**查看"摘要"** 页，然后单击"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="d95dc-183">Click **Next** to review the **Summary** page, then click **Finish**.</span></span>
    
<span data-ttu-id="d95dc-184">项目由项目创建Visual Studio，您将在"解决方案资源管理器"窗口中看到两个项目。</span><span class="sxs-lookup"><span data-stu-id="d95dc-184">After the project is created by Visual Studio, you will see two projects in the Solution Explorer window.</span></span> <span data-ttu-id="d95dc-185">第一个项目是 COM 加载项的项目;第二个项目是一个部署 COM 加载项的安装项目。</span><span class="sxs-lookup"><span data-stu-id="d95dc-185">The first project is the project for the COM Add-in; the second project is a setup project for deploying the COM Add-in.</span></span> <span data-ttu-id="d95dc-186">**共享外接程序向导** 仅插入对 **Microsoft Office 14.0** 对象库的引用，因此有必要使用以下步骤插入对 InfoPath 对象库的引用：</span><span class="sxs-lookup"><span data-stu-id="d95dc-186">The **Shared Add-in Wizard** only inserts a reference to the **Microsoft Office 14.0 Object Library**, so it is necessary to insert a reference to the InfoPath object library using the following steps:</span></span>
  
1. <span data-ttu-id="d95dc-187">双击"**我的Project"** 显示外接程序项目属性。</span><span class="sxs-lookup"><span data-stu-id="d95dc-187">Double-click **My Project** to display the add-in project properties.</span></span> <span data-ttu-id="d95dc-188">单击" **引用** "选项卡以显示自动添加到项目中的引用。</span><span class="sxs-lookup"><span data-stu-id="d95dc-188">Click the **References** tab to display the references automatically added to the project.</span></span> 
    
2. <span data-ttu-id="d95dc-189">单击" **添加** "按钮以显示" **添加引用** "对话框。</span><span class="sxs-lookup"><span data-stu-id="d95dc-189">Click the **Add** button to display the **Add Reference** dialog box.</span></span> 
    
3. <span data-ttu-id="d95dc-190">在 **"COM"** 选项卡上，双击 **"Microsoft.InfoPath 2.0 类型库"，** 然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="d95dc-190">On the **COM** tab, double-click **Microsoft.InfoPath 2.0 Type Library**, and click **OK**.</span></span>
    
4. <span data-ttu-id="d95dc-191">添加对 Microsoft **InfoPath 3.0** 类型库的引用也会添加对必须删除的三个程序集的引用 **：ADODB、MSHTML** 和 **MSXML2。** </span><span class="sxs-lookup"><span data-stu-id="d95dc-191">Adding a reference to the **Microsoft InfoPath 3.0 Type Library** also adds references to three assemblies that must be removed: **ADODB**, **MSHTML**, and **MSXML2**.</span></span> <span data-ttu-id="d95dc-192">在 **"解决方案资源管理器\*\*\*\*"中的**"引用"下，右键单击其中每个引用，然后单击"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="d95dc-192">In **Solution Explorer** under **References**, right-click each of these references, and then click **Remove**.</span></span>
    
## <a name="viewing-the-registry-settings"></a><span data-ttu-id="d95dc-193">查看注册表设置</span><span class="sxs-lookup"><span data-stu-id="d95dc-193">Viewing the Registry Settings</span></span>

<span data-ttu-id="d95dc-194">若要查看安装 COM 加载项时将创建的注册表设置，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="d95dc-194">To view the registry settings that will be created when the COM Add-in is installed, follow these steps:</span></span>
  
1. <span data-ttu-id="d95dc-195">右键单击"解决方案资源管理器"中安装程序项目的根节点，单击"查看"，再单击"**编辑器\*\*\*\*"，然后单击"注册表"。**</span><span class="sxs-lookup"><span data-stu-id="d95dc-195">Right-click the root node of the setup project in the **Solution Explorer**, click **View**, then **Editor**, then click **Registry**.</span></span>
    
2. <span data-ttu-id="d95dc-196">在左侧窗格中，单击加号以展开 **HKEY_LOCAL_MACHINE、Software、Microsoft、InfoPath** 和 **AddIns。**  </span><span class="sxs-lookup"><span data-stu-id="d95dc-196">In the left-hand pane, click the plus to expand **HKEY_LOCAL_MACHINE**, **Software**, **Microsoft**, **InfoPath**, then **AddIns**.</span></span>
    
3. <span data-ttu-id="d95dc-197">单击与共享加载项项目的 **ProgID 对应的名称**。</span><span class="sxs-lookup"><span data-stu-id="d95dc-197">Click the name corresponding to your shared add-in project's **ProgID**.</span></span>
    
<span data-ttu-id="d95dc-198">若要更改其中任何属性，请右键单击该属性，单击"属性窗口"，然后更改"属性窗口"中的"值 **"框**。</span><span class="sxs-lookup"><span data-stu-id="d95dc-198">To change any of these properties, right-click the property, click **Properties Window**, and change the **Value** box in the **Properties Window**.</span></span>
  
## <a name="compiling-and-distributing-the-shared-add-in"></a><span data-ttu-id="d95dc-199">编译和分发共享Add-In</span><span class="sxs-lookup"><span data-stu-id="d95dc-199">Compiling and Distributing the Shared Add-In</span></span>

<span data-ttu-id="d95dc-200">若要编译托管 COM 加载项以在开发共享 Add-In 项目的计算机上进行测试，请在"解决方案资源管理器"中右键单击"共享 Add-In"项目的根节点，然后单击"生成"。</span><span class="sxs-lookup"><span data-stu-id="d95dc-200">To compile the managed COM Add-in for testing on the computer on which the Shared Add-In project was developed, right-click the root node of the Shared Add-In project in the Solution Explorer and click Build.</span></span> <span data-ttu-id="d95dc-201">如果生成项目时没有出现错误，您可以启动 InfoPath 编辑环境并开始使用托管 COM 加载项。</span><span class="sxs-lookup"><span data-stu-id="d95dc-201">If the project builds with no errors, you can start the InfoPath editing environment and begin using the managed COM Add-in.</span></span> <span data-ttu-id="d95dc-202">如果正在运行 InfoPath 实例，则先关闭它，然后再生成项目。</span><span class="sxs-lookup"><span data-stu-id="d95dc-202">If you have an instance of InfoPath running, close it before building the project.</span></span> <span data-ttu-id="d95dc-203">可能还需要打开"COM 加载项"对话框来验证 COM 加载项是否注册。</span><span class="sxs-lookup"><span data-stu-id="d95dc-203">It may also be necessary to open the COM Add-ins dialog box to verify that the COM Add-in is registered.</span></span> <span data-ttu-id="d95dc-204">若要打开"COM 加载项"对话框，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="d95dc-204">To open the COM Add-ins dialog box, follow these steps:</span></span>
  
1. <span data-ttu-id="d95dc-205">打开 InfoPath 编辑环境。</span><span class="sxs-lookup"><span data-stu-id="d95dc-205">Open the InfoPath editing environment.</span></span> <span data-ttu-id="d95dc-206">执行此操作的最简单方法是打开现有 表单模板，这将基于该表单创建一表单模板。</span><span class="sxs-lookup"><span data-stu-id="d95dc-206">The easiest way to do this is to open an existing form template, which will create a new form based on that form template.</span></span>
    
2. <span data-ttu-id="d95dc-207">单击 **"工具"菜单** 上的" **信任中心** "。</span><span class="sxs-lookup"><span data-stu-id="d95dc-207">Click **Trust Center** on the **Tools** menu.</span></span> 
    
3. <span data-ttu-id="d95dc-208">单击 **左侧的"** 加载项"类别。</span><span class="sxs-lookup"><span data-stu-id="d95dc-208">Click the **Add-ins** category on the left.</span></span> 
    
4. <span data-ttu-id="d95dc-209">在"**信任** 中心"对话框底部附近的"管理"部分，从列表中选择 **"COM** 加载项"，然后单击"开始 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="d95dc-209">In the **Manage** section near the bottom of the **Trust Center** dialog box, select **COM Add-ins** from the list and click the **Go** button.</span></span> 
    
5. <span data-ttu-id="d95dc-210">在 **"COM 加载项** "对话框中，你将看到最近构建的加载项的名称，旁边应该有一个复选框。</span><span class="sxs-lookup"><span data-stu-id="d95dc-210">In the **COM Add-ins** dialog box, you will see the name of your recently-built add-in and there should be a check box next to it.</span></span> <span data-ttu-id="d95dc-211">如果旁边没有复选框，则 COM 加载项因错误而无法加载，该错误将在对话框的"加载行为"部分列出。 </span><span class="sxs-lookup"><span data-stu-id="d95dc-211">If there is no check box next to it, the COM Add-in failed to load due to an error, which will be listed in the **Load Behavior** section of the dialog box.</span></span> 
    
<span data-ttu-id="d95dc-212">若要编译托管 COM 加载项，以用于开发共享 Add-In 项目的计算机，必须执行其他步骤以确保代码安全。</span><span class="sxs-lookup"><span data-stu-id="d95dc-212">To compile the managed COM add-in for use on a computer other than the computer on which the Shared Add-In project was developed, you must follow additional steps to secure your code.</span></span> <span data-ttu-id="d95dc-213">有关保护共享Add-In项目以用于其他计算机的信息，请参阅以下三篇文章：</span><span class="sxs-lookup"><span data-stu-id="d95dc-213">For information on securing Shared Add-In projects for use on other computers, see the following three articles:</span></span>
  
- [<span data-ttu-id="d95dc-214">在 Office XP 中Add-Ins COM Office</span><span class="sxs-lookup"><span data-stu-id="d95dc-214">Deployment of Managed COM Add-Ins in Office XP</span></span>](https://go.microsoft.com/fwlink/?LinkID=73473)
  
- [<span data-ttu-id="d95dc-215">使用 COM 加载项填充程序解决方案在 OFFICE XP 中部署托管 COM 加载项</span><span class="sxs-lookup"><span data-stu-id="d95dc-215">Using the COM Add-in Shim Solution to Deploy Managed COM Add-ins in Office XP</span></span>](https://go.microsoft.com/fwlink/?LinkID=73474)
  
- [<span data-ttu-id="d95dc-216">使用 COM 填充Office隔离扩展</span><span class="sxs-lookup"><span data-stu-id="d95dc-216">Isolating Office Extensions with the COM Shim Wizard</span></span>](https://go.microsoft.com/fwlink/?LinkID=73475)
  
> [!IMPORTANT]
> <span data-ttu-id="d95dc-217">不隔离 COM 加载项可能会导致内存泄漏和应用程序不稳定。</span><span class="sxs-lookup"><span data-stu-id="d95dc-217">Not isolating the COM Add-in may cause memory leaks and application instability.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d95dc-218">如果.NET Framework安装项目中的程序集或其他所需程序集尚未安装在目标计算机上，.msi文件可能无法正确安装。</span><span class="sxs-lookup"><span data-stu-id="d95dc-218">If the .NET Framework or other required assemblies from the setup project are not already installed on target computers, the .msi file may not install properly.</span></span> <span data-ttu-id="d95dc-219">此外，无法分发.msi文件，然后尝试安装.msi文件。</span><span class="sxs-lookup"><span data-stu-id="d95dc-219">Also, you cannot distribute the .msi file and then attempt to install the .msi file.</span></span> <span data-ttu-id="d95dc-220">还必须将其他支持文件分发到由 Visual Studio 生成的原始 .msi 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="d95dc-220">You must also distribute the other support files in the same folder as the original .msi file generated by Visual Studio.</span></span> 
  
## <a name="coding-in-the-com-add-in"></a><span data-ttu-id="d95dc-221">COM 加载项中的编码</span><span class="sxs-lookup"><span data-stu-id="d95dc-221">Coding in the COM Add-in</span></span>

<span data-ttu-id="d95dc-222">COM 加载项可以捕获 InfoPath 表单编辑环境中发生的应用程序事件。</span><span class="sxs-lookup"><span data-stu-id="d95dc-222">Application events that occur in the InfoPath form editing environment can be captured by a COM Add-in.</span></span> <span data-ttu-id="d95dc-223">COM 加载项可以使用 [ApplicationEvents](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.ApplicationEvents.aspx) 对象的以下事件来响应用户操作：</span><span class="sxs-lookup"><span data-stu-id="d95dc-223">The following events of the [ApplicationEvents](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.ApplicationEvents.aspx) object can be used by the COM Add-in to respond to user actions:</span></span> 
  
|<span data-ttu-id="d95dc-224">**Event**</span><span class="sxs-lookup"><span data-stu-id="d95dc-224">**Event**</span></span>|<span data-ttu-id="d95dc-225">**说明**</span><span class="sxs-lookup"><span data-stu-id="d95dc-225">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d95dc-226">[NewXDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.NewXDocument.aspx) 事件</span><span class="sxs-lookup"><span data-stu-id="d95dc-226">[NewXDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.NewXDocument.aspx) Event</span></span>  <br/> |<span data-ttu-id="d95dc-227">新建表单时发生。</span><span class="sxs-lookup"><span data-stu-id="d95dc-227">Occurs when a new form is created.</span></span>  <br/> |
|<span data-ttu-id="d95dc-228">[Quit](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.Quit.aspx) 事件</span><span class="sxs-lookup"><span data-stu-id="d95dc-228">[Quit](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.Quit.aspx) Event</span></span>  <br/> |<span data-ttu-id="d95dc-229">用户退出 InfoPath 时发生。</span><span class="sxs-lookup"><span data-stu-id="d95dc-229">Occurs when the user quits InfoPath.</span></span>  <br/> |
|<span data-ttu-id="d95dc-230">[WindowActivate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.WindowActivate.aspx) 事件</span><span class="sxs-lookup"><span data-stu-id="d95dc-230">[WindowActivate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.WindowActivate.aspx) Event</span></span>  <br/> |<span data-ttu-id="d95dc-231">在激活文档窗口时发生。</span><span class="sxs-lookup"><span data-stu-id="d95dc-231">Occurs when any document window is activated.</span></span>  <br/> |
|<span data-ttu-id="d95dc-232">[WindowDeactivate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.WindowDeactivate.aspx) 事件</span><span class="sxs-lookup"><span data-stu-id="d95dc-232">[WindowDeactivate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.WindowDeactivate.aspx) Event</span></span>  <br/> |<span data-ttu-id="d95dc-233">在文档窗口成为非活动窗口时发生。</span><span class="sxs-lookup"><span data-stu-id="d95dc-233">Occurs when any document window is deactivated.</span></span>  <br/> |
|<span data-ttu-id="d95dc-234">[WindowSize](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.WindowSize.aspx) 事件</span><span class="sxs-lookup"><span data-stu-id="d95dc-234">[WindowSize](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.WindowSize.aspx) Event</span></span>  <br/> |<span data-ttu-id="d95dc-235">当调整任一文档窗口大小或移动该窗口时发生。</span><span class="sxs-lookup"><span data-stu-id="d95dc-235">Occurs when any document window is resized or moved.</span></span>  <br/> |
|<span data-ttu-id="d95dc-236">[XDocumentBeforeClose](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentBeforeClose.aspx) 事件</span><span class="sxs-lookup"><span data-stu-id="d95dc-236">[XDocumentBeforeClose](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentBeforeClose.aspx) Event</span></span>  <br/> |<span data-ttu-id="d95dc-237">在打开的文档即将关闭之前发生。</span><span class="sxs-lookup"><span data-stu-id="d95dc-237">Occurs immediately before any open document closes.</span></span>  <br/> |
|<span data-ttu-id="d95dc-238">[XDocumentBeforePrint](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentBeforePrint.aspx) 事件</span><span class="sxs-lookup"><span data-stu-id="d95dc-238">[XDocumentBeforePrint](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentBeforePrint.aspx) Event</span></span>  <br/> |<span data-ttu-id="d95dc-239">在即将打印任一打开文档时发生。</span><span class="sxs-lookup"><span data-stu-id="d95dc-239">Occurs immediately before any open document is printed.</span></span>  <br/> |
|<span data-ttu-id="d95dc-240">[XDocumentBeforeSave](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentBeforeSave.aspx) 事件</span><span class="sxs-lookup"><span data-stu-id="d95dc-240">[XDocumentBeforeSave](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentBeforeSave.aspx) Event</span></span>  <br/> |<span data-ttu-id="d95dc-241">在即将保存任一打开文档时发生。</span><span class="sxs-lookup"><span data-stu-id="d95dc-241">Occurs immediately before any open document is saved.</span></span>  <br/> |
|<span data-ttu-id="d95dc-242">[XDocumentChange](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentChange.aspx) 事件</span><span class="sxs-lookup"><span data-stu-id="d95dc-242">[XDocumentChange](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentChange.aspx) Event</span></span>  <br/> |<span data-ttu-id="d95dc-243">新建表单、打开现有表单或另一个表单变为激活状态时发生。</span><span class="sxs-lookup"><span data-stu-id="d95dc-243">Occurs when a new form is created, when an existing form is opened, or when another form is made the active form.</span></span>  <br/> |
|<span data-ttu-id="d95dc-244">[XDocumentOpen](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentOpen.aspx) 事件</span><span class="sxs-lookup"><span data-stu-id="d95dc-244">[XDocumentOpen](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentOpen.aspx) Event</span></span>  <br/> |<span data-ttu-id="d95dc-245">在打开文档时发生。</span><span class="sxs-lookup"><span data-stu-id="d95dc-245">Occurs when a document is opened.</span></span>  <br/> |
   
<span data-ttu-id="d95dc-246">若要在 COM 加载项中捕获这些事件，必须在 连接 类 **中声明以下类级别** 变量：</span><span class="sxs-lookup"><span data-stu-id="d95dc-246">To capture these events in the COM Add-in, you must declare the following class-level variables in your **Connect** class:</span></span> 
  
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

<span data-ttu-id="d95dc-247">第一行将加载项收到的通用应用程序 **对象** 强制转换到 _Application3 [对象。](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._Application3.aspx)</span><span class="sxs-lookup"><span data-stu-id="d95dc-247">The first line casts the generic application **Object** received by the add-in to the [_Application3](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._Application3.aspx) object.</span></span> <span data-ttu-id="d95dc-248">第二行将 **_Application3** 对象的 [Events](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._Application3.Events.aspx) (由 **InfoPathApplication** 变量) [ApplicationEvents](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.ApplicationEvents.aspx)对象。</span><span class="sxs-lookup"><span data-stu-id="d95dc-248">The second line casts the [Events](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._Application3.Events.aspx) property of the **_Application3** object (represented by the **InfoPathApplication** variable) to the [ApplicationEvents](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.ApplicationEvents.aspx) object.</span></span> 
  
<span data-ttu-id="d95dc-249">若要创建事件处理程序，请从 Visual Studio 窗口顶部的"类名称"下拉框中选择 **InfoPathApplicationEvents，** 然后在 Visual Studio 窗口顶部的"方法名称"下拉框中选择要处理的事件。</span><span class="sxs-lookup"><span data-stu-id="d95dc-249">To create event handlers, select **InfoPathApplicationEvents** from the **Class Name** drop-down box at the top of the Visual Studio window, and then select the event you want to handle in the **Method Name** drop-down box at the top of the Visual Studio window.</span></span> <span data-ttu-id="d95dc-250">例如，如果需要控制窗体保存时间，可以处理 **XDocumentBeforeSave** 事件。</span><span class="sxs-lookup"><span data-stu-id="d95dc-250">For example, if you need to control when a form is saved, you handle the **XDocumentBeforeSave** event.</span></span> <span data-ttu-id="d95dc-251">从 **"方法名称"下拉列表中选择"XDocumentBeforeSave"** 将自动插入以下过程： </span><span class="sxs-lookup"><span data-stu-id="d95dc-251">Selecting **XDocumentBeforeSave** from the **Method Name** drop-down automatically inserts the following procedure:</span></span> 
  
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

<span data-ttu-id="d95dc-252">**ApplicationEvents** 对象的任何事件都可以通过 COM 加载项使用相同的方法进行处理。</span><span class="sxs-lookup"><span data-stu-id="d95dc-252">Any of the events of the **ApplicationEvents** object can be handled by the COM Add-in using the same method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d95dc-253">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d95dc-253">See also</span></span>

- [<span data-ttu-id="d95dc-254">创建 Microsoft Office 2000 COM 加载项</span><span class="sxs-lookup"><span data-stu-id="d95dc-254">Creating a Microsoft Office 2000 COM Add-in</span></span>](https://go.microsoft.com/fwlink/?LinkID=73468) 
- [<span data-ttu-id="d95dc-255">使用 .NET Office托管 COM Add-Ins Visual Studio托管 COM 应用程序</span><span class="sxs-lookup"><span data-stu-id="d95dc-255">Creating Office Managed COM Add-Ins with Visual Studio .NET</span></span>](https://go.microsoft.com/fwlink/?LinkID=73470)
- [<span data-ttu-id="d95dc-256">使用 IDTExtensibility2 事件过程</span><span class="sxs-lookup"><span data-stu-id="d95dc-256">Working with the IDTExtensibility2 Event Procedures</span></span>](https://go.microsoft.com/fwlink/?LinkID=73471)
- [<span data-ttu-id="d95dc-257">使用 .NET Office COM 加载项Visual Basic加载项</span><span class="sxs-lookup"><span data-stu-id="d95dc-257">Build an Office COM Add-in With Visual Basic .NET</span></span>](https://go.microsoft.com/fwlink/?LinkID=73469)
- [<span data-ttu-id="d95dc-258">使用 Visual Office .NET 生成 C# COM 加载项</span><span class="sxs-lookup"><span data-stu-id="d95dc-258">Build an Office COM add-in by using Visual C# .NET</span></span>](https://support.microsoft.com/en-us/help/302901/how-to-build-an-office-com-add-in-by-using-visual-c-net)
- [<span data-ttu-id="d95dc-259">使用 Add-Ins System Visual Studio 的 Visual Studio 2005 工具创建 InfoPath 2007 Office 标准版</span><span class="sxs-lookup"><span data-stu-id="d95dc-259">Creating InfoPath 2007 Add-Ins by Using Visual Studio 2005 Tools for the Office System SE</span></span>](https://msdn.microsoft.com/library/bb968857%28office.12%29.aspx)

