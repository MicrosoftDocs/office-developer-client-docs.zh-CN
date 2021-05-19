---
title: 创建 Project Server 工作流以用于需求管理
manager: soliver
ms.date: 08/10/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: b0e4a3b3-d1df-454d-b74c-b980b0b456f6
description: 本文介绍如何使用 Designer 2013 SharePoint简单工作流。
ms.openlocfilehash: bbefc5d30ccb508a24c32fe41e733e6e8187ecd9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355497"
---
# <a name="create-a-project-server-workflow-for-demand-management"></a>创建 Project Server 工作流以用于需求管理

本文介绍如何使用 Designer 2013 SharePoint简单工作流。 您可以将工作流导出到 Visio 2013 进行可视化和编辑，或使用 Visio 2013 设计 Project Server 2013 工作流，将设计导入 SharePoint Designer 2013 中以发布给 Project Web App。 有关 SharePoint 工作流平台以及使用 Visio 2013 和 SharePoint Designer 2013 创建工作流的信息，请参阅 SharePoint [2013](https://msdn.microsoft.com/library/jj163986%28office.15%29.aspx)开发人员文档中的 workflows in SharePoint 2013 文章。 
  
有关为工作流准备 Project Server 的信息，请参阅[Start： Set up and configure SharePoint 2013 工作流管理器。](https://msdn.microsoft.com/library/jj163276%28office.15%29.aspx)

<a name="pj15_CreateWorkflowSPD_General"> </a>

## <a name="creating-a-general-workflow"></a>创建常规工作流

使用以下步骤通过 Project Designer 2013 创建 SharePoint Server 2013 工作流。 工作流设计用于项目建议的需求管理。
  
有关详细步骤，请参阅 [创建分支工作流部分](#pj15_CreateWorkflowSPD_Detailed) 。 
  
### <a name="to-create-a-project-server-workflow-general-procedure"></a>若要创建 Project Server 工作流 (一) 

1. 确定要求，然后设计工作流。 将工作流组织到阶段和阶段，并确定工作流将使用的自定义域。
    
2. 在Project Web App中，创建工作流所需的实体：
    
    1. 查看现有工作流阶段;创建阶段。
        
    2. 创建工作流将使用的企业自定义域。 若要在工作流阶段可用，自定义域必须受工作流控制。
        
    3. 编辑或创建 PDP (项目详细信息) ，您的工作流阶段将使用这些页面来收集项目的信息。 本示例中，阶段使用编辑的默认 PDP 来包括新的自定义域。
        
    4. 创建必要的工作流阶段，然后将每个工作流阶段与正确的阶段关联。
    
3. 在 SharePoint Designer 2013 中，使用基于文本的设计器中的声明性 **语句构造工作流**：
    
    > [!NOTE]
    > 您还可以切换到 SharePoint Designer  2013 中的可视化设计器，或从 Visio 2013 导入现有工作流。 请按照以下步骤使用基于 **文本的设计器**： 
    > 
    > 1. 打开 Project Web App 网站，然后创建一个使用 **SharePoint 2013 Workflow - Project Server 工作流** 平台的网站工作流。 
    > 2. 添加工作流使用的阶段。
    > 3. 插入每个阶段所需的工作流步骤、条件、操作和循环。
    > 4. 检查是否有工作流错误，并修复您找到的任何错误。
    > 5.  (可选) 将视图切换到 **可视化** 设计器，或将工作流导出到 Visio 2013 文件。 您可以修改Visio视图，并保存对当前工作流的更改。 您可以编辑该Visio文件，并导入到 SharePoint Designer 2013 中以创建其他工作流。
    > 6. 发布工作流。 发布后，工作流会显示在网站工作流Project Web App列表中。
    
4. 在Project Web App中，使用工作流进行项目建议的需求管理：
    
    1. 使用工作流的 EPT (创建) 模板。
        
    2. 在Project中心"页上，创建一个对工作流使用 EPT 的项目，然后执行工作流阶段。
        
    3. 全面测试工作流。
        
    4. 将工作流部署到生产服务器。

<a name="pj15_CreateWorkflowSPD_Detailed"> </a>

## <a name="creating-a-branching-workflow"></a>创建分支工作流

必须先将 工作流管理器 Client 1.0 服务配置为使用 Project Server 2013 工作流活动，然后才能使用 SharePoint Designer 2013 创建 Project Server 工作流。 若要了解如何配置 工作流管理器 Client 1.0，请参阅 SharePoint Server [2013 开发人员文档中的 SharePoint 2013](https://msdn.microsoft.com/library/jj163986%28office.15%29.aspx)中的工作流文章。 
  
以下详细过程包含的步骤与"创建常规工作流" [部分的步骤](#pj15_CreateWorkflowSPD_General) 相同。 
  
### <a name="to-create-a-project-server-branching-workflow-detailed-procedure"></a>若要创建 Project Server 分支工作流， (过程) 

#### <a name="1-plan-and-design-the-workflow"></a>1. 规划并设计工作流。

一Project服务器工作流可以在需求管理过程中与多个阶段集成。 由于工作流可能很复杂，因此您必须了解业务要求并仔细规划工作流。 对于简单示例，设计一个分支工作流，该工作流使用项目建议的估计成本来确定建议是否被接受。 如果估计成本大于 25，000 美元，则拒绝该建议;否则，接受建议并创建项目。
    
因为您可以使用 Visio 2013 和 SharePoint Designer 2013 来帮助设计和创建 Project Server 2013 的工作流，所以与 Project Server 2010 一样，您可以更轻松地对工作流进行试验。 本文中的示例工作流设计与 Project 2010 SDK 中的创建分支工作流一文相同。 [](https://msdn.microsoft.com/library/a02cafdc-d881-4271-b446-d8b2cd456a52%28Office.15%29.aspx) 您可以使用 Project Web App 测试实例在远程计算机上设计和创建测试工作流，而不需要在 Project Server 2013 计算机上直接创建工作流。 
    
#### <a name="2-create-the-entities-that-your-workflow-requires"></a>2. 创建工作流所需的实体。

在Project Web App中，查看可用的工作流阶段和阶段以及可用的企业自定义域。 如有必要，创建工作流所需的实体，如以下步骤所示：
    
1. **工作流阶段** 默认安装的 Project Web App包括创建、选择、计划、管理和完成阶段。 对于分支工作流示例，不需要创建其他阶段。 
        
2. **Enterprise自定义字段** 分支工作流需要一个受工作流控制的项目成本自定义域。 工作流控制的自定义域的值在工作流使用的 PDP 中设置。 例如，选择设置页面右上角的"Project Web App"图标，选择"PWA 设置"，然后选择"自定义Enterprise字段和查找 **表"。**
        
   为实体创建一个名为"建议成本 **Project，然后选择** 类型 **Cost**。 对于说明，键入项目建议的估计成本。 在"**行为"** 部分，选择 **"工作流控制的行为"。**
        
3. **Project详细信息页面** 编辑或创建工作流阶段将使用的 PDP。 例如，执行下列步骤： 
        
    1. 在 **"Project"** 页上选择"设置详细信息页面"，然后选择 **"ProjectInformation** PDP"。 
            
    2. 在功能 **区的"页面**"选项卡上的"编辑 **"** 组中，选择"编辑 **页面"。**
            
    3. 选择基本信息 Web 部件右上方的向下箭头，然后选择"编辑 Web **部件"。** 或者，在功能区的 **"WEB 部件**"选项卡上的"属性"组中，选择 **"Web** 部件属性"以显示编辑器部件。 
            
    4. 在编辑器 **Project** 的"显示字段"部分 (图 1) "修改 **"。**
            
    5. 添加"**建议** 成本"自定义域，将其移动到"所选字段"列表中的"所有者 **"Project"** 上方，然后选择"确定 (参见图 1) 。
      
    6. 在编辑器部件中，选择"**确定**"，然后在功能区的"**页面**"选项卡上的"编辑"组中选择"停止编辑"。 图 2 显示了添加到"建议 **成本**"自定义域Project信息 PDP。 

    **图 1.编辑 PDP Project字段 Web 部件**

    ![编辑 PDP Project]字段 Web 部件(media/pj15_CreateWorkflowSPD_EditPDP.gif "编辑 PDP") Project字段 Web 部件

    **图 2.编辑的 PDP 包括"建议成本"自定义域**

    ![编辑的 PDP 包括"建议成本"字段]编辑的(media/pj15_CreateWorkflowSPD_EditedPDP.gif "PDP 包括\"建议成本\"字段")
  
4. **工作流阶段** 创建工作流每个阶段所需的阶段。 在"服务器设置"页上，选择"**工作流阶段"，** 然后选择"**新建工作流阶段"。** 图 3 显示了"添加工作流阶段"页的一部分。
    
    **图 3.在工作流中添加工作流Project Web App**

    ![在工作流中添加工作流Project Web App](media/pj15_CreateWorkflowSPD_AddWorkflowStage.gif "在工作流中添加工作流Project Web App")
  
    分支工作流示例使用表 1 中显示的四个阶段。 在图 3 **设置** 中未 ("添加工作流阶段"页的"可见Project详细信息页"部分，) 可选;它们在"工作流状态"页上提供了详细信息。 例如，由于"初始建议详细信息"PDP 需要用户输入，因此可以选中 **"Project 详细信息** 页面需要关注"复选框，然后添加特定说明，如设置此 PDP 的项目名称和成本。
    
    图 4 显示了"工作流阶段"页上完成的四个阶段。
    
    **表 1.分支工作流的阶段**

    |名称|说明|提交说明|阶段|可见的 PDP|自定义字段|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |初始建议详细信息  <br/> |设置项目名称和成本。  <br/> |将项目作为建议提交。  <br/> |创建  <br/> |Project信息  <br/> Project详细信息  <br/> |建议所需的 (成本)   <br/> |
    |Project详细信息  <br/> |提供建议项目的详细信息。  <br/> |提交详细信息以继续项目。  <br/> |创建  <br/> |Project信息  <br/> Project详细信息  <br/> |建议 (只读)   <br/> |
    |自动拒绝  <br/> |根据提供的信息，将拒绝建议。  <br/> | <br/> |创建  <br/> |Project信息  <br/> |建议 (只读)   <br/> |
    |执行  <br/> |该建议被接受，并且已准备好进行项目管理。  <br/> | <br/> |管理  <br/> |Project信息  <br/> Project详细信息  <br/> |建议 (只读)   <br/> |
   
    **图 4.工作流中的工作流Project Web App**

    ![Project Web App](media/pj15_CreateWorkflowSPD_WorkflowStages.gif "")中的工作流阶段列表Project Web App
  
#### <a name="3-construct-the-workflow-in-the-text-based-designer"></a>3. 在工作流设计器中Text-Based工作流。

在 SharePoint Designer 2013 中，使用 Text-Based Designer 中的声明性语句构造工作流。 可以在橙色插入行开始键入，获取工作流逻辑和步骤的上下文相关自动完成语句，或者可以使用功能区"工作流"选项卡上的"插入"组中控件插入逻辑和步骤。   
    
1. 在 SharePoint Designer 2013 的 Backstage 视图中，选择"**打开网站"。** 例如，打开  `https://ServerName/pwa` 。 在导航 **窗格中**，选择"工作流 **"。** 然后，在功能区的 **"工作流**"选项卡上的 **"新建"** 组中，选择"网站 **工作流"。** 对于此示例，将工作流命名为 Branching Workflow。 确保 **"SharePoint 2013 工作流 - Project 服务器**"在"平台类型"下拉列表中选中 (请参阅图 5) 。 
    
    **图 5.创建 Project Server 网站工作流**

    ![创建 Project Server 网站工作流](media/pj15_CreateWorkflowSPD_CreateSiteWorkflow.gif "创建 Project Server 网站工作流")
  
2. 选择"**分支工作流"** 选项卡。然后，在功能 **区的"工作流**"选项卡上的"管理"组中，在"视图"下拉列表中，选择"**基于文本的设计器"。** 若要使用闪烁的橙色插入行显示视图 (请参阅图 6) ，请单击视图内。
    
    **图 6.使用Text-Based设计器视图**

    ![Using the Text-Based Designer view]Using the Text-Based Designer(media/pj15_CreateWorkflowSPD_TextBasedDesigner.gif "view")
  
3. 在" **基于文本的设计器"** 视图中，添加工作流使用的阶段。 在功能 **区的"工作流**"选项卡上的"插入"组中，在"创建"下的"阶段"下拉列表中，选择"初始 **建议详细信息"。** 
    
    同样，将橙色插入行放在"阶段 **：** 初始建议详细信息"框下方，并添加工作流使用的其他阶段 **：Project Details、Automated** **Rejection** 和 **Execution** (请参阅图 7) 。 
    
    **图 7.在工作流设计器中向工作流SharePoint阶段**

    ![在 SPD 中向工作流添加阶段](media/pj15_CreateWorkflowSPD_AddStageInSPD.gif "向 SPD 中的工作流添加阶段")
  
4. 在每个阶段中添加工作流步骤和逻辑： 
    
    1. 在" **初始建议详细信息** "阶段，将橙色插入行放在阶段正文的顶部。 在功能 **区上的**"插入"组中，选择"操作"，向下滚动到"Project Web App **操作**"，然后选择"等待 **Project事件"。** 选择 **此项目事件**，然后选择" **事件： 在** 下拉列表中提交项目时"。 
    
    2. 在"**初始建议详细信息**"阶段的"转换到阶段 **"部分，** 插入 **"如果任何值等于值"。** 您可以开始键入语句或使用功能区上的"插入"**组中"** 条件"控件。 
    
    3. 选择第一 **个值** 控件，然后选择 **fx** 以显示"定义工作流查找" (请参阅图 8) 。 在"**数据源"** 下拉列表中，选择"Project **数据"。** 在"**源域"** 下拉列表中，选择"**建议成本"。**
    
       **图 8.在工作流中定义查找值**

       ![在工作流中定义查找值](media/pj15_CreateWorkflowSPD_DefineWorkflowLookup.gif "定义工作流中的查找值")
  
    4. 完成 `If` 该语句，以便显示以下内容：如果 **Project：建议成本大于 25000**
    
       > [!NOTE]
       > 或者，您可以创建一个工作流变量，将该变量设置为自定义字段值，然后将该变量与值进行比较。 例如，从功能 **区** 上的"局部变量"下拉列表中，创建一个名为 **"TotalCost"** 的变量， (") "类型的 **变量**。 在"**定义工作流查找**"对话框中，为数据源选择"工作流变量和参数"，然后选择"**变量： TotalCost"** 作为字段。 If 语句随后为 **：If Variable： TotalCost 大于 25000**
  
    5. 将橙色插入行放在分支中，然后使用"操作"控件在功能区上的"插入"组中插入"转到 `If` 阶段"。    选择 **"阶段"** 下拉列表控件并选择"自动 **拒绝"** 阶段。 
    
       同样，在 `Else` 分支中，插入"转到 **Project Details"** 语句。 图 9 显示了已完成的初始 **建议详细信息** 阶段。 
    
       **图 9.初始建议详细信息阶段的已完成逻辑**

       ![初始建议详细信息的]已完成逻辑(media/pj15_CreateWorkflowSPD_InitialStageLogic.gif "初始建议详细信息的已完成逻辑")
  
    6. 在 **"自动拒绝"** 阶段，除非您希望暂停工作流，在 PDP 中显示一些数据，否则请保留第一部分为空。 " **转换到阶段** "部分必须包含转换;由于拒绝后没有其他阶段，请为语句键入"转到工作流结束"。 
    
    7. 在 **"Project详细信息**"阶段，在"转换到阶段 **"部分添加"执行**"。 除非有要添加的其他数据，或者您希望暂停工作流，否则无需等待已提交事件。 
    
    8. 在 **"执行** "阶段，除非您希望暂停工作流，否则请保留"阶段操作"部分为空。 在"**转换到阶段"** 部分，添加 **"转到工作流结束"。**
    
5. 在功能 **区上的"** 保存"组中，选择"检查错误"以检查工作流 (请参阅图 10) 。 修复所有错误，然后选择"保存 **"。**
    
    **图 10.在工作流设计器中检查SharePoint错误**

    ![检查工作流中的错误](media/pj15_CreateWorkflowSPD_SPDCheckForErrors.gif "检查工作流中的错误")
  
6.  (可选) 在功能区的"管理"组中，在"视图"下拉菜单中，选择"**可视化设计器"。** 在图 11 中，视图缩小到 50%。
    
    您可以使用可视化设计器编辑工作流中的项目。 例如，选择"如果 **任何值等于** 值"条件，选择条件左下角的工具图标，然后选择"值"以显示"属性"对话框中 **的比较条件**。 
    
    **图 11.将可视化设计器用于工作流**

    ![使用Visio设计视图]使用工作流的Visio(media/pj15_CreateWorkflowSPD_SwitchView.gif "设计视图")
  
    当工作流位于可视化设计器视图中时，若要将 Visio 2013 (.vsdx) 文件保存为备份或供以后使用，您可以选择"导出到 **Visio"。**
    
7. 发布工作流。 当您使用 SharePoint Designer 2013 将工作流发布到活动的 Project Web App 网站时，工作流将注册到 SharePoint 网站或 Azure 中，并且将在 Project Web App 中用于新的 ETS。

#### <a name="4-create-an-ept-for-the-workflow-and-then-test-the-workflow"></a>4. 为工作流创建 EPT，然后测试工作流。

在Project Web App中，为工作流创建 EPT，然后通过创建项目建议来测试工作流：
    
1. On the PWA 设置 page， choose **Enterprise Project Types**， and then create an EPT named Test Branching Workflow. 清除 **"新建项目SharePoint** 任务列表项目"复选框，以便 Project Server 将保持对 EPT 所创建项目的完全控制。 在"网站工作流关联"下拉列表中选择"分支工作流"，然后选择"新建 **Project** 页面"**下拉列表中的"Project** 信息 PDP"作为工作流显示的第一页。 
    
    **图 12.为工作流添加 EPT**

    ![为工作流添加 EPT](media/pj15_CreateWorkflowSPD_EPTs.gif "为工作流添加 EPT")
  
    > [!NOTE]
    > 企业 **项目类型** 表中的"SharePoint 任务列表 **Project"** 列中的"是"值是指创建 SharePoint 任务列表的 EPT，其中任务列表在 Project Web App 中可见，但 SharePoint 维护对项目的控制。 有关将项目作为任务列表SharePoint，请参阅 Project [Server 2013 体系结构](project-server-2013-architecture.md)。 
  
2. 打开项目中的"项目"Project Web App，然后使用新的 EPT (创建项目，请参阅图 13) 。 因为 **测试分支工作流** 与分支 **工作流关联**，所以项目创建在工作流的控制下开始。
    
    **图 13.使用测试分支工作流 EPT 创建项目**

    ![使用 EPT 创建](media/pj15_CreateWorkflowSPD_NewProject.gif "项目使用 EPT 创建项目")
  
3. 当工作流显示"Project **信息** PDP"时，将数据添加到项目字段。 例如，输入建议 **成本** 值 30000。 美国英语版本的 Project Server 将字段更改为显示 $30，000 (请参阅图 14) 。
    
    **图 14.使用已编辑Project信息 PDP**

    ![使用已编辑Project信息 PDP](media/pj15_CreateWorkflowSPD_NewProjectStage1.gif "Using the edited Project Information PDP")
  
4. 在功能 **区的"项目**"选项卡上的 **"Project"组中**，选择"保存 **"。** Project服务器将 PDP 中的数据添加到项目中，然后显示"工作流状态"页 (图 15) 。 To see the full description of the Initial Proposal Details stage in the workflow status diagram， hover the pointer over the stage in the workflow visualization diagram.
    
    " **所有工作流阶段"** 网格使用绿色箭头显示"初始建议详细信息"阶段正在等待输入。 这是因为工作流在"初始建议详细信息"阶段等待提交事件。 如果工作流未等待提交事件，可以在"页面"组中选择"下一步"以前进到下一个 PDP。 
    
    **图 15.使用"初始建议详细信息"阶段中的"工作流状态"页**

    ![第一阶段后的第一阶段](media/pj15_CreateWorkflowSPD_NewProjectStage1Status.gif "\"工作流状态\"页后的\"工作流状态\"页")
  
    工作流可视化图以绿色显示当前阶段。 在" **创建** "阶段，"初始建议详细信息"阶段是当前阶段。 
    
5. 在功能区的"**工作流"组中**，选择"提交 **"。**
    
    > [!TIP]
    > 如果 **"提交** "控件被禁用，则刷新页面。 
  
    如果 **"建议成本** "值大于 25，000 美元，工作流将移动到"自动拒绝"阶段。 图 16 显示再次选择"提交"时"自动拒绝 **"阶段** 状态。 如果 **建议成本** 为 25，000 美元或更少，则工作流将移至 Project 详细信息 (参见图 17) 。 
    
    **图 16.工作流在"自动拒绝"阶段完成**

    ![在自动拒绝中完成工作流](media/pj15_CreateWorkflowSPD_AutomatedRejectionCompleted.gif "在自动拒绝中完成工作流")
  
    图 17 显示了另一个包含名为 **Test 2 - Branching** 的项目建议的测试，其中Project详细信息阶段是"创建"阶段中的当前阶段。 "管理"阶段以浅蓝色显示，这表示阶段尚未处于活动状态。
    
    **图 17.如果成本低于 25，000 美元Project工作流将继续进入"详细信息"阶段**

    !["详细信息"阶段](media/pj15_CreateWorkflowSPD_ProjectDetailsStage.gif "Project\"详细信息")"阶段的工作流Project状态
  
6. 如果前进到"Project"阶段，则默认页面中不会添加其他数据。 再次 **选择"** 提交"以前进到"执行 (请参阅图 18) 。 
    
    **图 18.工作流已准备好在"执行"阶段管理**

    !["执行"阶段中的](media/pj15_CreateWorkflowSPD_ExecutionStage.gif "工作流状态\"执行\"阶段的\"工作流状态\"")
  
在Project详细信息"阶段，工作流不会等待提交事件。 如果Project详细信息 PDP 包含其他必填字段，Project服务器将一直等待，直到向字段添加数据，然后再继续执行阶段。 如分支工作流中的定义，执行阶段也不等待提交事件。 在"执行"阶段，您可以作为项目经理编辑项目，或在功能区的"**项目**"选项卡中选择"关闭"。 When you choose **Close**， you can check in the project and edit it later or leave the project checked out.

分支 **工作流** 项目是一个只有一个比较测试的简单示例。 工作流涉及"创建"阶段的三个阶段和需求管理的"管理"阶段的一个阶段。 若要全面测试工作流，应测试工作流的所有分支，并使用极端和典型的值查看行为是否如预期一样。 

<a name="pj15_CreateWorkflowSPD_ImportingVromVisio"> </a>

## <a name="importing-a-workflow-from-visio"></a>从工作流导入Visio

若要更改工作流，您可以创建或修改工作流控制的自定义域，以及创建或修改工作流阶段和阶段。 您可以使用 SharePoint Designer 2013 添加条件、操作、循环和阶段，然后保存和重新发布工作流。 若要重用或保留工作流的备份，您可以将它导出到 Visio 2013 文件中。 
  
您还可以在 Visio 2013 创建或编辑工作流，将该文件导入 SharePoint Designer 2013 中供 Project Web App。 若要使用未经修改的工作流，Project Web App实例必须包含与原始工作流实例中的工作流Project Web App属性相同。 有关使用工作流Visio创建工作流的信息，请参阅[Workflow development in SharePoint Designer 2013 and Visio 2013。](https://msdn.microsoft.com/library/jj163272%28office.15%29.aspx)
  
> [!NOTE]
> 当您将 Visio 2013 文件导入到 Project Web App 的不同实例时，即使阶段名称相同，阶段也具有不同的阶段 GUID。 导入工作流后，必须将阶段属性和操作属性配置为使用特定于该工作流实例Project Web App值。 
> 
> 如果您在 Visio 2013 中创建了工作流，则阶段和操作没有特定于 Project Web App 实例的属性，因为 Visio 未与 Project Web App 连接。 当您将 SharePoint Designer 2013 与 Project Web App、创建工作流，然后导入 VSDX 文件时，将覆盖活动工作流。 然后，您必须配置阶段和操作属性，以匹配 Designer 2013 SharePoint 2013 Project Web App。 
  
### <a name="to-import-a-workflow-from-visio-to-sharepoint-designer"></a>将工作流从 Visio 导入SharePoint Designer

1. 在 Visio 2013 中，创建一个简单的工作流。 例如，执行下列步骤：
    
   1. 打开Visio，然后创建工作流。 选择新工作流的 **"类别**"窗格，选择"流程图"，在"新建"窗格中选择 **"Microsoft SharePoint 2013** 工作流"模板，然后选择"创建 **"。**  工作流将打开一个名为 Stage **1** 的 Stage 形状。 工作流包括"开始"组件以及进入形状和退出形状作为阶段形状的一部分。
    
      当您将鼠标悬停在"阶段"形状上并选择" **属性** "图标时，将禁用所选内容。 在将工作流图导入到 Designer 2013 后，可以设置SharePoint和操作属性。 
    
      > [!NOTE]
      >  您唯一应该使用的形状模具是流程图形状列表中的以下形状： 
      > - **操作 - SharePoint 2013 工作流**
      > - **组件 - SharePoint 2013 工作流**
      > - **条件 - SharePoint 2013 工作流**
  
   2. 在"**形状"** 窗格中，选择"**快速** 形状"，然后将名为"如果任何值等于值的条件"形状拖到"阶段"形状的右侧。 
    
   3. 在功能 **区的"** 开始"选项卡上，选择"连接线"工具，然后将阶段中的退出形状与"条件"形状 (请参阅图 19) 。 
    
      **图 19.在工作流程图中将阶段形状与条件Visio连接**

      ![在"在工作流Visio](media/pj15_CreateWorkflowSPD_NewVisioWorkflow.gif "创建工作流图表Visio")
  
   4. 将两个其他阶段形状拖动到条件形状的右侧。 这些形状名为 Stage **2** 和 **Stage 3。**
    
   5. 使用 **连接器** 工具，将条件形状的右侧连接到进入第 **2 阶段的形状**。 选择 **指针** 工具，双击连接以显示名称的文本框，然后将连接名称为"是"。
    
   6. 连接条件形状的底部到进入第 **3 阶段的形状**。 使用指针 **工具**，右键单击连接，**然后选择否。** 这两种方法都适用于将连接器 **命名为"是**"或"**否"。**
    
   7. 在"形状"窗格中，选择"操作 - **SharePoint 2013** 工作流"，然后将"等待项目事件"操作拖到第 **1** 阶段的形状中间 (请参阅图 20) 。 
    
      **图 20.在工作流中Visio**

      ![在工作流中Visio](media/pj15_CreateWorkflowSPD_CompletedVisioWorkflow.gif "在工作流中完成Visio")
  
   8. 在功能 **区的"流程**"选项卡上的 **"图表验证**"组中，选择"**检查图表"。** 修复所有错误，然后保存绘图。 例如，将文件从 Visio.vsdx 命名。
    
      有关修复工作流错误的信息，请参阅[Troubleshooting SharePoint Server 2013 workflow validation errors in Visio 2013](https://msdn.microsoft.com/library/jj163971%28v=office.15%29.aspx)。
    
2. 打开SharePoint Designer 2013"，然后打开Project Web App"分支工作流"示例所使用的同一 **网站**。 
    
3. 在 **导航** 窗格中 **选择"** 工作流"，然后创建网站工作流 **(功能区的**"工作流"选项卡上的"网站工作流") 。 例如，从"简单工作流"中将工作流Visio。
    
   在"**创建网站工作流**"对话框中，确保平台类型为 SharePoint **2013 Workflow - Project Server。** 选择 **"创建**"，SharePoint"**设计器"打开** 新工作流的"基于文本的设计器"窗格。 
    
4. 在功能 **区的**"**工作流"选项卡** 上的"管理"组中，选择"工作流 **设置"。**
    
5. 在功能 **区的**"**工作流设置**"选项卡上的"管理"组中，选择"从 Visio 导入 **"，** 然后从之前保存的 **Visio.vsdx** 文件导入测试工作流。 "Microsoft **SharePoint** 设计器"对话框警告您导入的图表不包含工作流属性，并询问是否覆盖当前工作流。 选择 **"是";选择"是"。** SharePoint设计器导入工作流图表，为形状生成模具，并显示包含导入的工作流的 **可视化** 设计器窗格。 
    
6. 设置工作流中每个阶段形状的属性。 例如，第一个阶段形状名为 Stage **1 (Invalid)**，因为它不表示连接的形状实例中的Project Web App阶段。 选择或悬停在阶段上时，可以选择阶段形状左下角的"属性"图标以显示"阶段属性"对话框 (参阅图 21) 。 在"**阶段"** 下拉列表 **中选择"初始** Project详细信息"阶段，然后选择"确定 **"。** SharePoint设计器重命名阶段。
    
   **图 21.在设计器中设置SharePoint属性**

   ![在导入的工作流中设置属性](media/pj15_CreateWorkflowSPD_ImportFromVisio1.gif "在导入的工作流中设置属性")
  
   对于第二阶段，将 Project **Stage** 属性设置为 **自动拒绝**。 对于第三阶段，将 Project **Stage** 属性设置为 **Execution**。
    
7. 同样，对于 **"等待项目事件"** 操作，将"**事件名称**"属性设置为 **"事件： 提交项目时"。**
    
8. 同样，设置 **If 任何值等于值条件** 的属性。 例如，将第一 **个 Value** 属性设置为 **Project Data：Proposal Cost 。** 将 **Operator** 属性设置为 **小于**。 将第二 **个 Value** 属性设置为 5000。
    
9. 检查工作流中的错误，然后保存工作流。 如果没有错误，您可以将视图更改为基于文本的 **设计器** (图 22) 。 
    
   **图 22.在工作流设计器中查看Text-Based工作流**

   ![查看导入的工作流](media/pj15_CreateWorkflowSPD_WorkflowFromVisio.gif "查看导入的工作流")
  
10. 发布工作流。 如果已保存工作流但不发布它，则当您创建企业项目类型时，工作流将不可用。
    
11. 若要测试 Project Web App中从 Visio 导入的简单工作流，请创建一个使用该工作流的 EPT，然后创建使用新 EPT 的项目，就像对分支工作流示例一样。 但是，在这种情况下，成本低于 5，000 美元的项目将被拒绝。 
    
在阅读本文时，您通过使用 SharePoint Designer 2013 直接设置工作流使用的阶段、条件和操作，创建并测试了一个简单的分支工作流。 您还可以使用 2013 为更简单的分支工作流创建Visio图。 您将工作流Visio导入到 SharePoint Designer 2013 中，其中您通过与 Project Web App 的连接设置每个阶段、条件和操作Project Web App。
  
Visio 2013 和 SharePoint Designer 共同为设计人员、项目经理、工作流开发人员和测试人员提供了一种便捷方式，以便创建、共享和自定义不同安装的 Project Server 2013 和 Project Online 的工作流设计。 对于需要以编程方式访问 Project SharePoint Designer 不提供的 Project Server 的工作流，可以将 Visual Studio 2012 与客户端对象模型 (CSOM) 。
  
## <a name="see-also"></a>另请参阅

- [Project Server 2013 体系结构](project-server-2013-architecture.md)
- [开始：设置和配置 SharePoint 2013 工作流管理器](https://msdn.microsoft.com/library/jj163276%28office.15%29.aspx)
- [了解如何在 SharePoint 2013 中打包和部署工作流](https://msdn.microsoft.com/library/jj819316%28office.15%29.aspx)
- [SharePoint 2013 中的工作流](https://msdn.microsoft.com/library/jj163986%28office.15%29.aspx)
- [SharePoint Designer 2013 和 Visio 2013 中的工作流开发](https://msdn.microsoft.com/library/jj163272%28office.15%29.aspx)
- [2013 SharePoint Server 2013 工作流验证Visio疑难解答](https://msdn.microsoft.com/library/jj163971%28v=office.15%29.aspx)
- [工作流和需求管理](https://msdn.microsoft.com/library/cf7433a3-a531-4467-ac0c-df0c5d6881ae%28Office.15%29.aspx)

