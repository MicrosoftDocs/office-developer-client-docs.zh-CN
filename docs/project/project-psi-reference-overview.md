---
title: 项目 PSI 参考概述
manager: soliver
ms.date: 09/17/2015
ms.audience: Developer
f1_keywords:
- Admin
- Archive
- Authentication
- Calendar
- CubeAdmin
- CustomFields
- Events
- LoginForms
- LoginWindows
- LookupTable
- Notifications
- ObjectLinkProvider
- Project
- Project Server Interface
- Project Server Web services
- PSI
- PSI reference
- PSI Web services
- PWA
- QueueSystem
- Resource
- ResourcePlan
- Rules
- Security
- Statusing
- StatusReports
- TimeSheet
- Version
- View
- Web service
- Web services
- WinProj
- WssInterop
keywords:
- web 服务，日历，身份验证 Web 服务，ResourcePlan，Web 服务，StatusReports，Web 服务，PSI、 命名空间、 事件处理程序，Project Server Web 服务，通知、 QueueSystem、 Web 服务，Project 2013 平台 LoginWindows，网站服务、 Web 服务、 进展状况、 Web 服务，资源、 WinProj、 Web 服务，WssInterop，Web 服务、 Web 服务，Winproj，事件处理程序，LookupTable，Web 服务，PWA 中，Web 服务、 Web 服务，安全性通知 Web 服务、 Web 服务时间表、 Web 服务，QueueSystem，PSI，Web 服务、 Web 服务、 事件、 PSI，编程，Web 服务，LookupTable、 版本控制、 Web 服务，CustomFields Web 服务、 Web 服务、 PWA PSI、 资源，Web 服务、 Web 服务、 ResourcePlan 时间表、 Web服务，Web 服务，规则 PSI，托管代码参考，安全，Web 服务的 PSI Web 服务，CustomFields URL、 Web 服务，WssInterop，Web 服务，管理，Web 参考 （英文），PSI，Web 服务，CubeAdmin，View，Web 服务，日历，Web 服务，Web查看、 管理服务、 Web 服务、 LoginForms、 Web 服务、 Web 服务，LoginForms、 PSI、 Url 和 ObjectLinkProvider、 Web 服务，存档，Web 服务，CubeAdmin，Web 服务，规则，Web 服务，Web 服务，身份验证 Web 服务，PSI，Project Server事件、 事件、 Web 服务、 Web 服务、 Project、 进展状况、 Web 服务、 Web 服务，ObjectLinkProvider、 Project Server 接口 Web 方法，PSI，Web 服务，StatusReports，Web 服务，存档、 项目、 Web 服务，Web 服务 LoginWindows
localization_priority: Normal
ms.assetid: d3c33089-0cbe-48c3-bfc0-0be819ca4d73
description: Project Server 接口 (PSI) 是用于开发与 Project Server 2013 本地集成的应用程序的 API。
ms.openlocfilehash: 14ab540fd8a66cf18c576572fc0eff4df7c7d61c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779557"
---
# <a name="project-psi-reference-overview"></a>项目 PSI 参考概述

Project Server 接口 (PSI) 是用于开发与 Project Server 2013 本地集成的应用程序的 API。
  
本文是记录的程序集、 命名空间，以及在 PSI 中的服务的概述。 [Project Server 2013 类类库和 web 服务引用](http://msdn.microsoft.com/library/ef1830e0-3c9a-4f98-aa0a-5556c298e7d1%28Office.15%29.aspx)SDK 中包含所有 PSI 和 Project Server 2013 中的[Microsoft.ProjectServer.Client](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.aspx)命名空间的托管的代码文档。 若要开发 for Project Online 中的应用程序，必须使用**Microsoft.ProjectServer.Client**命名空间而非 PSI。 

Project Server 2013 中的 PSI 具有双重接口。 Web 服务的 ASMX 接口定义的发现和 Web 服务描述语言 （disco 和 WSDL） 文件中`http://ServerName/ProjectServerName/_vti_bin/psi/`（例如，Projectdisco.aspx 和 Projectwsdl.aspx） 的虚拟目录。 您可以仅通过 Project Web App 的本地安装的 URL 访问 ASMX 接口 (例如， `http://ServerName/ProjectServerName/_vti_bin/psi/project.asmx?wsdl)`。 若要在浏览器中显示的 web 服务，必须包括`?wsdl`URL 选项。 由于 ASMX 接口内置中使用 Windows Communication Foundation (WCF) 基础结构，Project Server web 服务的.asmx 文件不实际 PSI 的虚拟目录中存在。 
  
WCF 服务接口定义的后端.svc 文件`http://ServerName:32843/GUID/PSI/`中的 SharePoint Web 服务应用程序虚拟目录。 Project Service 应用程序虚拟目录中的 URL 的 PSI 服务 (例如， `http://ServerName:32843/GUID/PSI/project.svc`) 包括.svc 文件。 但是，不能直接用于后端 URL 设置 WCF 服务引用。 若要开发应用程序或使用 PSI 的 WCF 服务的组件，您可以使用代理程序集或代理文件。 Project Server 2013 中的 Project 2013 SDK 下载包括用于 WCF 服务的代理文件，并脚本来获取更新的 WCF 代理文件并将这些文件编译为代理程序集的较新的 Project Server 构建。
  
Project Service 应用程序目录名称是一个 GUID 值，该值与相同的本地 Project Web App 实例的 GUID。 在**Internet 信息服务 (IIS) 管理器**窗口中，展开**SharePoint Web 服务**节点，选择 GUID 目录名，，然后选择要复制的**虚拟路径**值的**高级设置**。 
  
> [!IMPORTANT]
> PSI 的 ASMX web 服务界面在 Project Server 2013 中已弃用，但仍然支持。 新的应用程序应使用 PSI 或 CSOM 的 WCF 接口。 有关已弃用的功能的详细信息，请参阅[Project 2013 中面向开发人员的更新](updates-for-developers-in-project-2013.md)
> 
> 新应用程序和仅在内部部署安装 Project Server 运行的中间件组件应使用 WCF 接口，这是建议的网络通信的技术。 使用 ASMX 接口的旧版应用程序必须使用通过 Project Web App，检查 Project Server 权限的 URL。 
> 
> 有关 ASMX 接口以及如何使用 WCF 接口的详细信息，请参阅[项目中的基于 ASMX 的代码示例的先决条件](prerequisites-for-asmx-based-code-samples-in-project.md)和[项目中的基于 WCF 的代码示例的先决条件](prerequisites-for-wcf-based-code-samples-in-project.md)。 
  
对于开发使用 WCF 接口的应用程序，您可以使用 Visual Studio 2010 或 Visual Studio 2012。 有关如何创建声明性的 Project Server 工作流，您可以使用 SharePoint Designer 2013。 可以使用 Visual Studio 2012 开发 project Server 工作流需要访问 PSI 或 CSOM。
  
### <a name="using-the-psi-reference"></a>使用 PSI 引用
<a name="pj15_PSIRefOverview_Using"> </a>

PSI 对象模型非常大，并且许多类和成员仅供内部使用。 因此，可以是令人费解的[Project Server 2013 类类库和 web 服务引用](http://msdn.microsoft.com/library/ef1830e0-3c9a-4f98-aa0a-5556c298e7d1%28Office.15%29.aspx)中查找所需的主题。 将用于开发的参考主题大部分是以下组中：
  
- **主要类的方法：** 在 PSI 中的每个服务包括主类，该类命名为服务的名称。 例如，**资源**服务包含一些[资源](https://msdn.microsoft.com/library/WebSvcResource.Resource.aspx)类，这是[WebSvcResource](https://msdn.microsoft.com/library/WebSvcResource.aspx)命名空间中。 要查看的**资源**类中可用的方法列表，请展开内容窗格中的类节点，然后选择**资源方法**主题。 
    
- **DataRow 属性：** 有许多主类方法使用或返回**数据集**。 **DataSet**中的每个**DataTable**对象包含一个或多个**DataRow**对象中的数据。 在大多数情况下，您需要查看只有一行属性，不是所有的**数据集**、 **DataTable**或**DataRow**类的其他成员。 例如， **ResourceAssignmentDataSet**类包含子类**ResourceAssignmentDataTable**和[ResourceAssignmentDataSet.ResourceAssignmentRow](https://msdn.microsoft.com/library/WebSvcResource.ResourceAssignmentDataSet.ResourceAssignmentRow.aspx)类。 要查看的位于**ResourceAssignmentRow**类的属性的列表，请展开内容窗格中的类节点，然后选择**ResourceAssignmentDataSet.ResourceAssignmentRow 属性**主题。 
    
除了服务命名空间， [Project Server 2013 类类库和 web 服务引用](http://msdn.microsoft.com/library/ef1830e0-3c9a-4f98-aa0a-5556c298e7d1%28Office.15%29.aspx)的主题链接到的第三方解决方案的开发中使用的三个 Project Server 程序集的本地安装。 我们提供这些程序集仅最少量文档。 PSI 引用文档的主要类和 23 公共服务中的成员。 六个 PSI 服务是仅，供内部使用，且未进行归档。 
  
> [!NOTE]
> 从 Project Server 程序集和服务，可以单独使用客户端对象模型 (CSOM) 中的类。 您可以从 Project Server 计算机上，在远程开发环境中使用**Microsoft.ProjectServer.Client**命名空间和开发与 Project Online 或内部部署安装 Project Server 的集成的应用程序。 但是，CSOM 包含完整的 PSI 的功能的子集。 CSOM 使开发 Project Server 集成的最常见方案。 有关详细信息，请参阅[What the CSOM does and 不可实现的操作](what-the-csom-does-and-does-not-do.md)并[Microsoft.ProjectServer.Client](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.aspx) 。 
  
对于大多数应用程序使用 PSI 开发，您不必开发的 Project Server 计算机上，或在全局程序集缓存中设置对 Project Server 程序集的引用。 您可以将必要的 Project Server 程序集复制到开发计算机。 Project Server 2013 安装以下程序集 _[Program Files]_ `\Microsoft Office Servers\15.0\Bin`: 
  
- Microsoft.Office.Project.Server.Events.Receivers.dll 
- Microsoft.Office.Project.Server.Library.dll
- Microsoft.Office.Project.Server.Workflow.dll
    
对 PSI 服务命名空间具有为 PSI 代理程序集，ProjectServerServices.dll，生成文档以便创建的任意名称。 在 PSI 引用中，每个服务命名空间具有占位符名称 （例如， _[项目 web 服务]_） 和 web 引用 (如`http://ServerName/ProjectServerName/_vti_bin/psi/Project.asmx?wsdl`)。 
  
## <a name="project-server-assemblies-and-namespaces"></a>Project Server 程序集和命名空间
<a name="pj15_PSIRefOverview_Assemblies"> </a>

安装 Project Server; 时即会安装多个程序集记录仅四个 Project Server 程序集。 第三方开发人员通常使用只有几类和成员中这些程序集。 未记录的 Project Server 程序集包含命名空间和类可用于 Project Web App，业务实体，如在内部，使用 Project Server 的类和数据访问层 (DAL)。 当为某个归档的 Project Server 程序集，可以在 Visual Studio 中设置的引用时，可以看到所有的命名空间、 类和 Visual Studio 对象浏览器中的成员。
  
> [!NOTE]
> 归档的 Project Server 命名空间的许多成员仅供内部使用且具有最少量文档。 
  
当 for Project Online 进行开发，您可以使用仅 CSOM 访问 Project Server 功能。 您没有对 PSI 服务或其他 Project Server 程序集的访问。
  
[Project Server 2013 类类库和 web 服务引用](http://msdn.microsoft.com/library/ef1830e0-3c9a-4f98-aa0a-5556c298e7d1%28Office.15%29.aspx)psi 包括可从以下程序集的命名空间： 
  
- **Microsoft.Office.Project.Server.Library.dll**该程序集包含一个归档的命名空间和三个未归档的命名空间，，如下所示： 
    
  - [Microsoft.Office.Project.Server.Library](https://msdn.microsoft.com/library/Microsoft.Office.Project.Server.Library.aspx)命名空间包括许多枚举和类字段和属性的常用于 Project server 的内部部署应用程序中。 例如，开发人员通常使用**CustomField.Type**，等**PSClientError**、 **PSErrorInfo**和**筛选器**类的枚举。 
    
    **Microsoft.Office.Project.Server.Library** 命名空间还包括以下七个属性类，它们包含 3,200 多个子类： 
    
      - **AssignmentProperties**  
      - **CalendarProperties**
      - **ConstraintProperties**
      - **LookupTableProperties**
      - **项目属性时**
      - **ResourceProperties**
      - **TaskProperties**
    
    属性类内部使用，且未进行归档。 属性类用于 Project Professional 2013 和 Project Server 之间的序列化。 当您使用 Visual Studio 中的**Microsoft.Office.Project.Server.Library**命名空间时，对象浏览器中显示的所有属性类，这将使更加难以找到的第三方开发有用的类。 第三方开发人员没有使用属性类，因为 SDK 将不记录。 
    
  - **Microsoft.Office.Project.Server.DataServices**的类和成员的有关此命名空间的内部用于 Project Online 中的**OData**服务访问 Project 数据库中的报告表。 **数据服务**类且未进行归档。 
    
  - **Microsoft.Office.Project.Server.Administration**类和成员该命名空间的内部用于诊断日志记录和未进行归档。 
    
  - **Microsoft.Office.Project.Server.Base**的类和此命名空间的成员内部用作基类，且未进行归档。 
    
  - **Microsoft.Office.Project.Server.Library.FilterSchema**该命名空间内部用来生成筛选器架构和未进行归档。 
    
- **Microsoft.Office.Project.Server.Workflow.dll**此程序集用于仍可在 Project Server 2013 中工作的旧 Project Server 2010 工作流。 创建新的工作流，您应使用 SharePoint Designer 2013，或您还可以通过以下方式使用 Visual Studio 2012 [Microsoft.ProjectServer.Client.WorkflowActivities](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.WorkflowActivities.aspx)类。 Microsoft.Office.Project.Server.Workflow.dll 程序集包括以下三个命名空间： 
    
  - [Microsoft.Office.Project.Server.Workflow](https://msdn.microsoft.com/library/Microsoft.Office.Project.Server.Workflow.aspx)此命名空间包括用于 Project Server 工作流活动类。 活动包括读取、 比较和更新项目属性。 其他类管理工作流和项目发生更改时包括工作流回调。 
    
  - **Microsoft.Office.Project.PWA**该命名空间包括 PSI，用于与 Project Web App 和自定义工作流活动; 的内部代理未进行归档。 
    
    自定义工作流活动需要对**Microsoft.Office.Project.PWA**若要访问所有 PSI 服务中的类的引用。 例如， **Microsoft.Office.Project.PWA.PSI**类包含**ProjectWebService**属性，其获取[WebSvcProject](https://msdn.microsoft.com/library/WebSvcProject.aspx)命名空间的代理。 
    
  - **Microsoft.Office.Project.Server.WebServiceProxy**此命名空间包括每个 PSI 服务中的主要类的内部代理类。 通过使用的工作流用户提升的权限，工作流可以呼叫通过代理类的 PSI 方法。 代理类且未进行归档。 
    
- **Microsoft.Office.Project.Server.Events.Receivers.dll**[Microsoft.Office.Project.Server.Events](https://msdn.microsoft.com/library/Microsoft.Office.Project.Server.Events.aspx)是此程序集中的唯一命名空间。 它包括事件接收器和事件参数类的 PSI 服务和其他内部类。 
    
  开发人员编写从事件接收器类派生的事件处理程序。PSI 服务中的大多数主类都具有一个对应的事件接收器类。例如，**ProjectEventReceiver** 类包含对应于 PSI 中的 **Project** 类中的方法的前期事件和后期事件接收器方法。**OnCreating** 方法和 **OnCreated** 方法分别是 **QueueCreateProject** 方法的前期事件接收器方法和后期事件接收器方法。 
    
  开发人员通常使用下列事件接收器类：
  <br/>  
  - [AdminEventReceiver](https://msdn.microsoft.com/library/Microsoft.Office.Project.Server.Events.AdminEventReceiver.aspx)
  - [CalendarEventReceiver](https://msdn.microsoft.com/library/Microsoft.Office.Project.Server.Events.CalendarEventReceiver.aspx)
  - [CubeAdminEventReceiver](https://msdn.microsoft.com/library/Microsoft.Office.Project.Server.Events.CubeAdminEventReceiver.aspx)
  - [CustomFieldsEventReceiver](https://msdn.microsoft.com/library/Microsoft.Office.Project.Server.Events.CustomFieldsEventReceiver.aspx)
  - [LookupTableEventReceiver](https://msdn.microsoft.com/library/Microsoft.Office.Project.Server.Events.LookupTableEventReceiver.aspx)
  - [ProjectEventReceiver](https://msdn.microsoft.com/library/Microsoft.Office.Project.Server.Events.ProjectEventReceiver.aspx)
  - [OptimizerEventReceiver](https://msdn.microsoft.com/library/Microsoft.Office.Project.Server.Events.OptimizerEventReceiver.aspx)
  - [ReportingEventReceiver](https://msdn.microsoft.com/library/Microsoft.Office.Project.Server.Events.ReportingEventReceiver.aspx)
  - [ResourceEventReceiver](https://msdn.microsoft.com/library/Microsoft.Office.Project.Server.Events.ResourceEventReceiver.aspx)
  - [SecurityEventReceiver](https://msdn.microsoft.com/library/Microsoft.Office.Project.Server.Events.SecurityEventReceiver.aspx)
  - [StatusingEventReceiver](https://msdn.microsoft.com/library/Microsoft.Office.Project.Server.Events.StatusingEventReceiver.aspx)
  - [TimesheetEventReceiver](https://msdn.microsoft.com/library/Microsoft.Office.Project.Server.Events.TimesheetEventReceiver.aspx)
  - [UserDelegationEventReceiver](https://msdn.microsoft.com/library/Microsoft.Office.Project.Server.Events.UserDelegationEventReceiver.aspx)
  - [WorkflowEventReceiver](https://msdn.microsoft.com/library/Microsoft.Office.Project.Server.Events.WorkflowEventReceiver.aspx)
  - [WssInteropEventReceiver](https://msdn.microsoft.com/library/Microsoft.Office.Project.Server.Events.WssInteropEventReceiver.aspx)
    
  **RulesEventReceiver**类和**StatusReportsEventReceiver**类均内部用于 Project Web App。 
    
- **Microsoft.ProjectServer.Client.dll**此程序集包含 CSOM 开发使用.NET Framework 4。 程序集位于`%ProgramFiles%\Common Files\Microsoft Shared\Web Server Extensions\15\ISAPI\Microsoft.ProjectServer.Client.dll`。 开发的应用程序使用**Microsoft.ProjectServer.Client**命名空间是独立的内部部署 Project Server Api 和服务，尽管应用程序可以使用以下任意本地或联机 Project Server 的安装。 对于可用于 Windows Phone 8 的相关 CSOM 程序集，Microsoft Silverlight 或 JavaScript 与 web 应用程序，请参阅[Microsoft.ProjectServer.Client](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.aspx) 。 
    
- **Microsoft.Office.Project.Server.Schema.dll** Project 2013 SDK 未记录中的**Microsoft.Office.Project.Server.Schema**命名空间`[Windows]\Microsoft.NET\assembly\GAC_MSIL\Microsoft.Office.Project.Schema\v4.0_15.0.0.0__71e9bce111e9429c\Microsoft.Office.Project.Schema.dll`程序集。 命名空间包含的 PSI 中, 使用的所有**数据集**、 **DataTable**和**DataRow**类以及许多其他 Project Server 内部使用的类似类的定义。 每个 PSI 服务中的公共类均编档在特定服务引用。 例如，介绍了**DriverDataSet.DriverRow**类[WebSvcDriver](https://msdn.microsoft.com/library/WebSvcDriver.aspx)命名空间中。 
    
  > [!NOTE]
  > 应用程序使用 CSOM、 使用远程事件处理程序，或访问 Project Online 不使用**Microsoft.Office.Project.Server.Schema**命名空间。 
  
  在使用完全信任事件处理程序的某些应用程序中（将事件处理程序安装到 Project Server 计算机上），必须设置对 Microsoft.Office.Project.Schema.dll 程序集的引用。下面是两个示例：
    
  - 在自定义域的完全信任 **OnCreated** 前期事件处理程序中，可以将 **e.CustomFieldInformation** 事件参数与对 **CustomFieldDataSet** 和 **CustomFieldsRow** 定义的 **Microsoft.Office.Project.Server.Schema** 命名空间的引用一起使用。 
   
     ```cs
        using PSLibrary = Microsoft.Office.Project.Server.Library;
        using Microsoft.Office.Project.Server.Schema;
        . . .
        // Event handler for the OnCreated event of a custom field.
        public override void OnCreated(
            PSLibrary.PSContextInfo contextInfo, 
            CustomFieldsPostEventArgs e)
        {
            // Get information from the event arguments. 
            string userName = contextInfo.UserName.ToString();
            CustomFieldDataSet customFieldDs = e.CustomFieldInformation;
            CustomFieldsRow customFieldRow = customFieldDs.CustomFields.Rows[0];
            string customFieldName = customFieldRow["MD_PROP_NAME"].ToString();
            byte customFieldType = (byte)customFieldRow["MD_PROP_TYPE_ENUM"];
            Guid customFieldUid = (Guid)customFieldRow["MD_PROP_UID"];
            . . .
        }
     ```

  - 自定义工作流活动可以要求对 **DataSet** 定义的 **Microsoft.Office.Project.Server.Schema** 的引用。 
    
## <a name="psi-services"></a>PSI 服务

<a name="pj15_PSIRefOverview_PSI"> </a>

PSI 的 WCF 服务和 Project Server 2013 的相同的 ASMX web 服务的一组。 若要使用 Visual Studio 项目中的服务，则设置引用的 URL`.svc`文件或`.asmx?wsdl`服务使用 nameservice 的任意名称。 Wsdl.exe 或 svcutil.exe 实用程序然后生成该命名空间，代理源代码和编译器创建要包含在您的应用程序的代理服务程序集。 
  
> [!NOTE]
> PSI 引用包括占位符 nameservice 名称，例如 _[管理 web 服务]_、 _[驱动程序 web 服务]_ 和 _[项目 web 服务]_ 的 PSI 服务。 每个 PSI nameservice 包括主类包含用于该服务的 web 方法。 例如，如果您设置**管理**服务的引用并将其命名为**WebSvcAdmin**，然后在您的应用程序**WebSvcAdmin** nameservice 包括具有**GetServerCurrency**的 web 方法的主要**管理**类**ListInstalledLanguages**、 **ReadServerVersion**，等等。 已弃用的 PSI 服务的列表，请参阅[Project 2013 中面向开发人员的更新](updates-for-developers-in-project-2013.md)。 
  
30 总的 PSI 服务的**身份验证**、 **ExchangeSync**、 **OData**、 **P12Upgrade**、 **psiserviceapp**、 **PWA**、**视图**和**WinProj**供内部使用的 Project Web App 和项目专业版和均未进行归档。 尽管您可以创建代理文件或包含 PSI 内部服务代理程序集，内部服务不用于第三方;PSI 引用不记录这些服务。 下图显示在 Internet 信息服务管理器的后端 PSI 服务的位置。 
  
**在 IIS 中查找 PSI 服务**

![在 IIS 管理器中的 PSI 服务](media/pj15_PSIReference_IIS.gif "在 IIS 管理器中的 PSI 服务")
  
以下是包含 PSI 服务中的 Web 方法的所有类：
  
1. [管理](https://msdn.microsoft.com/library/WebSvcAdmin.Admin.aspx)**Project Server 管理**页在 Project Web App 中包括所使用的方法。 定义财政年度，管理 statusing 和货币设置报告时间段、 的审核日志和 Active Directory 设置。 
    
2. [存档](https://msdn.microsoft.com/library/WebSvcArchive.Archive.aspx)包含用于管理的项目、 安全类别、 自定义字段、 资源、 系统设置、 视图和企业全局项目备份和还原方法。 读取并更新存档计划。 对所有项目进行都存档或删除指定的存档的项目。 将备份对象保存到的存档数据库表和还原备份到的已发布数据库表的对象。 
    
3. **身份验证**包含用于仅供 Project Professional 和 Project Web App 内部使用的方法。 
    
4. [日历](https://msdn.microsoft.com/library/WebSvcCalendar.Calendar.aspx)管理企业日历例外。 签出和签入资源日历。 创建、 删除、 列出所有、 更新或返回日历例外。 
    
5. [CubeAdmin](https://msdn.microsoft.com/library/WebSvcCubeAdmin.CubeAdmin.aspx)管理 OLAP 多维数据集设置。 获取分析服务器和数据库的状态，多维数据集的列表。 将多维数据集生成服务请求放在队列中。 读取并更新计算的成员的定义和维度和多维数据集中的度量值字段设置。 
    
6. [CustomFields](https://msdn.microsoft.com/library/WebSvcCustomFields.CustomFields.aspx)管理企业自定义域。 包括签出和签入方法，创建、 读取、 更新和删除 (CRUD) 方法的企业自定义域。 
    
7. [驱动程序](https://msdn.microsoft.com/library/WebSvcDriver.Driver.aspx)管理项目组合分析驱动因素和项目创建和需求管理驱动因素优先顺序。 包括项目驱动因素的 CRUD 方法。 
    
8. [事件](https://msdn.microsoft.com/library/WebSvcEvents.Events.aspx)管理 Project Server 事件处理程序关联。 包含用于 Project Server 事件处理程序关联的特定事件，或所有事件处理程序关联的 CRUD 方法。 
    
9. **ExchangeSync**这是一项内部的 Project Server 服务处理 Exchange 服务器的事件。 Project Web App 使用**ExchangeSync**同步而不是直接与 Outlook 客户端与 Office Project Server 2007 同步的 Project Server 和 Exchange Server 之间的工作分配。 
    
    只能通过 **ProjectServiceApplication** URL 访问 **ExchangeSync** 服务。第三方开发不支持 **ExchangeSync** 类和成员。 
    
10. [LoginForms](https://msdn.microsoft.com/library/WebSvcLoginForms.LoginForms.aspx)使用基于表单的身份验证提供**登录**和**注销**方法。 只有在前端的 Project Web App 网站访问**LoginForms**服务才可用。 
    
11. [LoginWindows](https://msdn.microsoft.com/library/WebSvcLoginWindows.LoginWindows.aspx)提供用于 Windows 身份验证与多个身份验证的基于 ASMX 的应用程序的**登录**和**注销**方法 (声明和基于表单的) Project Server 2013 安装。 只有在前端的 Project Web App 网站访问**LoginWindows**服务才可用。 
    
    > [!CAUTION]
    > 基于 WCF 的应用程序或在仅使用声明身份验证或 **OAuth** 的 Project Server 安装中运行的应用程序不使用 **LoginWindows** 服务；在上述情况下，**Login** 方法始终返回 **false**。声明身份验证将处理集成 Windows 身份验证。 
  
12. [LookupTable](https://msdn.microsoft.com/library/WebSvcLookupTable.LookupTable.aspx)管理查阅表格、 多语言查阅表格和其对应的代码掩码。 签出，签入、 读取、 创建、 删除和更新。 
    
13. [通知](https://msdn.microsoft.com/library/WebSvcNotifications.Notifications.aspx)管理通知和提醒。 包含用于获取、 设置、 注册和注销警报结果方法。 
    
14. [ObjectLinkProvider](https://msdn.microsoft.com/library/WebSvcObjectLinkProvider.ObjectLinkProvider.aspx)管理 web 对象和链接的文档和 SharePoint 网站上的列表项。 创建、 删除或读取项目链接的项目、 任务链接的 web 对象。 
    
    > [!NOTE]
    > Project Server 2013 中已弃用**ObjectLinkProvider** service。 有关详细信息，请参阅[Project 2013 中面向开发人员更新](updates-for-developers-in-project-2013.md)中的*已否决功能*一节。 
  
15. **OData**报告表和视图提供内部的**OData**接口。 可通过后端**ProjectServiceApplication** URL 仅对**OData**服务的访问。 PSI 中的专用**OData**服务提供了一种方法， **ODataClient.ProcessOdataMessage**，Project Server 内部使用处理请求的报表数据。 HTTP 请求穿过前端**ProjectData**服务。 
    
    有关**ProjectData**服务和 OData 协议用于读取报表数据的信息，请参阅[ProjectData-Project OData 服务引用](https://msdn.microsoft.com/en-us/library/office/jj163015.aspx)。
    
16. **P12Upgrade**提供用于 Project Server 2013 安装程序以将 Office Project Server 2007 安装升级的内部方法。 访问**P12Upgrade**服务位于只能通过**ProjectServiceApplication** URL。 **P12Upgrade**方法不支持第三方开发。 
    
17. [PortfolioAnalyses](https://msdn.microsoft.com/library/WebSvcPortfolioAnalyses.PortfolioAnalyses.aspx)包括针对项目相关性、 优化器、 规划器以及分析解决方案的 CRUD 方法。 
    
18. [项目](https://msdn.microsoft.com/library/WebSvcProject.Project.aspx)管理项目。 签出，签入、 创建、 删除、 读取，或更新的 Project 数据库草稿表或已发布的表中的项目。 将一条消息置于发布的队列。 
    
    创建或删除项目 （任务、 资源、 工作分配等） 中的实体。 获取信息或更新的项目工作组或项目网站的地址。 获取其中资源具有工作分配的项目状态，在草稿表格、 所有的摘要任务、 任务分配给指定的资源可用或所有项目的项目的列表。
    
    创建和管理提交，创建项目建议和 SharePoint 任务列表中的项目以及查找项目/主项目关系。
    
19. **psiserviceapp**在内部使用 Project Online。 不支持第三方开发**psiserviceapp**类和成员。 
    
20. **PWA**包含为 Project Web App，包括任务更新审批规则和管理状态报告的方法进行了优化的许多方法。 通常专门**PWA**方法并与其他 PSI 服务中的等效方法的 ア ネ 较冗余比较。 **PWA**方法使用或返回许多其他 PSI 方法为相同的数据集。 
    
    只能通过 **PWA** URL 访问 **ProjectServiceApplication** 服务。第三方开发不支持 **PWA** 类和成员。 
    
21. [QueueSystem](https://msdn.microsoft.com/library/WebSvcQueueSystem.QueueSystem.aspx)管理 Project Server 队列。 获取指定项目作业计数、 作业和作业组等待时间、 所有作业、 指定的作业、 所拥有的呼叫者，作业或作业的状态。 管理作业关联和配置队列。 
    
22. [资源](https://msdn.microsoft.com/library/WebSvcResource.Resource.aspx)管理企业资源。 签出、 签入、 更新或创建资源或 Project Server 用户和其授权设置;查找资源名称或 GUID。读取资源或用户数据和资源细分结构 (RBS) 和相关的安全信息;获取所有工作分配的资源，则和重置用户密码。 **资源**类包含用于用户委派的 CRUD 方法。 
    
23. [ResourcePlan](https://msdn.microsoft.com/library/WebSvcResourcePlan.ResourcePlan.aspx)管理资源计划。 检出、 签入、 发布，并包括用于资源计划的 CRUD 方法。 
    
24. [安全](https://msdn.microsoft.com/library/WebSvcSecurity.Security.aspx)包含用于安全模板、 安全类别、 组织和全局权限和组权限的 CRUD 方法。 **安全**类包含的项目类别的方法。 
    
25. [进展状况](https://msdn.microsoft.com/library/WebSvcStatusing.Statusing.aspx)管理状态更新和工作分配。 状态更新或审批应用、 提交状态更新、 设置提交的更新的摘要信息、 删除已批准的状态更新或审核历史记录指定用户，或者删除一组项目的所有状态信息。 创建、 获取，或委派分配;设置工作分配工作持续时间。 获取当前用户; 的新工作分配获取工作分配或任务事务历史记录、 按时间分段的实际值，或摘要任务层次结构。 
    
    预览或导入时间表数据，或读取用户的工作计划和非工作计划。查找挂起的状态更新、已提交更新的信息或已提交更新中的更改的事务记录。读取团队状态。
    
26. [时间表](https://msdn.microsoft.com/library/WebSvcTimeSheet.TimeSheet.aspx)管理时间表。 包括用于时间表的 CRUD 方法和提交或调用时间表。 查找时间表的最晚或挂起的审批;查找按日期或时间段的时间表。 获取时间表审批者的列表。 将时间表实际值和验证将时间表行。 **时间表**类包括**ReadProjectTimesheetLines**方法和读取和提交另一个资源的时间表，而无需模拟的**SubmitTimesheetLines**方法。 
    
27. **视图****查看**服务仅在 Project Web App 内使用设计。 **View**类中的方法管理视图和查看报告和阅读视图中的字段。 
    
    只能通过 **ProjectServiceApplication** URL 访问 **View** 服务。第三方开发不支持 **View** 方法。 
    
28. **WinProj****WinProj**服务只能通过 Project Professional 设计用于。 第三方开发人员不应使用**WinProj**方法使用 Project Server 进行编程。 
    
    一些 **WinProj** 方法使用的数据集（如 **ProjectRelationsDataSet** 和 **ResourceDataSet**）与 **Project** 和 **Resource** 服务使用的数据集相同，但前者需要 Project Professional 中的特定属性和功能。 
    
    只能通过 **ProjectServiceApplication** URL 访问 **WinProj** 服务。第三方开发不支持 **WinProj** 方法。 
    
29. [工作流](https://msdn.microsoft.com/library/WebSvcWorkflow.Workflow.aspx)包括企业项目类型和管理工作流阶段的 CRUD 方法。 运行工作流、 设置状态信息并管理需求管理工作流中的项目详细信息页面 (PDP) 阶段。 若要开发 Project Server 工作流，开发人员可以对声明性工作流中使用 SharePoint Designer 2013 或用于 Visual Studio 2012 开发使用.NET Framework 4 和[的 Office 开发人员工具Microsoft.ProjectServer.Client.WorkflowActivities](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.WorkflowActivities.aspx)中 CSOM 的类。 
    
30. [WssInterop](https://msdn.microsoft.com/library/WebSvcWssInterop.WssInterop.aspx)管理项目网站。 创建和删除项目网站。 获取的信息和更新 SharePoint 设置和管理网站。 同步并更新项目网站成员身份和组。 
    
每个服务命名空间包括所有服务使用的**数据集**架构和事件处理程序类。 例如， `Calendar.svc` (或`Calendar.asmx?wsdl`asmx web 服务) 介绍**日历**服务。 如果 name 引用**WebSvcCalendar**，代理命名空间包含主**日历**方法**CheckInCalendars**类、 **CheckOutCalendars**，等等。 **WebSvcCalendar**代理命名空间还包括**CalendarDataSet**类及其所有及其子类别。 
  
某些 PSI 服务包含重复的 **DataSet** 类。例如，**Project** 服务和 **Statusing** 服务都包括 **ProjectDataSet** 类。这是因为，**Project** 服务和 **Statusing** 服务中的方法都包括对 **ProjectDataSet** 的引用，而在设置引用和编译应用程序时创建的代理程序集包括相关的数据集。**Project** 服务和 **Statusing** 服务需要 **ProjectDataSet.ProjectRow** 类中的不同域的值。 
  
例如，在浏览 PSI 引用的命名空间和类时，若要查看 **Project** 服务的 Web 方法，请展开“目录”**** 列表中的“[Project web service]”**** 命名空间，然后展开 **Project** 类。 
  
## <a name="see-also"></a>另请参阅

- [Project Server 2013 体系结构](project-server-2013-architecture.md)
- [Project Server 可编程性](project-server-programmability.md)   
- [PSI 执行和不执行的操作](what-the-psi-does-and-does-not-do.md)   
- [在项目中的基于 ASMX 的代码示例的先决条件](prerequisites-for-asmx-based-code-samples-in-project.md)   
- [在项目中的基于 WCF 的代码示例的先决条件](prerequisites-for-wcf-based-code-samples-in-project.md)   
- [.NET Framework 开发人员中心](http://msdn.microsoft.com/en-us/netframework/aa496123.aspx)
    

