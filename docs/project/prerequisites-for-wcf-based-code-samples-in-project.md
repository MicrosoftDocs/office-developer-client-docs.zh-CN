---
title: Project 中基于 WCF 的代码示例的先决条件
manager: soliver
ms.date: 09/17/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 60d2afc8-10b6-465d-8ce8-c073da6e5054
description: 了解可帮助您在 Visual Studio 中创建项目的信息, 方法是使用 Project Server Interface (PSI) 参考主题中包含的基于 WCF 的代码示例。
ms.openlocfilehash: 2222e1b3651044c41f45e57481f80093aac67bdb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357149"
---
# <a name="prerequisites-for-wcf-based-code-samples-in-project"></a>Project 中基于 WCF 的代码示例的先决条件

了解可帮助您在 Visual Studio 中创建项目的信息, 方法是使用 Project Server Interface (PSI) 参考主题中包含的基于 WCF 的代码示例。
   
[project Server 2013 类库和 web 服务引用](https://msdn.microsoft.com/library/ef1830e0-3c9a-4f98-aa0a-5556c298e7d1%28Office.15%29.aspx)中包含的许多基于 WCF 的代码示例最初都是为 project 2010 开发人员文档创建的, 并对 WCF web 服务使用标准格式。 该示例仍适用于 Project Server 2013, 并设计为将其复制到控制台应用程序中并作为一个完整的单元运行。 示例中注明了例外情况。 
  
project 2013 开发人员文档中的代码示例在为 Office Project Server 2007 开发的示例中保持不变。使用 .asmx Web 服务。 此外，可以修改基于 ASMX 的示例以使用 WCF 服务。 本文演示如何使用使用 WCF 服务的示例。 有关如何将示例与 .asmx web 服务一起使用的信息, 请参阅[Project 中基于 .asmx 的代码示例的先决条件](prerequisites-for-asmx-based-code-samples-in-project.md)。
  
> [!NOTE]
> 如果客户端对象模型 (CSOM) 包括您的应用程序所需的方法，则应使用 CSOM 开发新的应用程序。 CSOM 使应用程序能够使用 project Online 或 project Server 2013 的本地安装。 否则，如果您的应用程序使用 PSI，则应使用我们为网络通信推荐的 WCF 接口技术。 使用 .asmx 接口或 WCF 接口的应用程序只能在本地安装的 Project Server 2013 中运行。 
>
> 有关 CSOM 的详细信息, 请参阅 project 2013 的[project Server 2013 体系结构](project-server-2013-architecture.md)和[客户端对象模型 (CSOM)](client-side-object-model-csom-for-project-2013.md)。 
  
在运行代码示例之前，您必须设置开发环境、配置应用程序、添加服务配置文件（或以编程方式配置 WCF 服务）并更改泛型常量值以与您的环境匹配。
  
## <a name="setting-up-the-development-environment"></a>设置开发环境
<a name="pj15_PrerequisitesWCF_Setup"> </a>

1. **设置测试 Project Server 系统。**
    
    在进行开发或测试时，请使用测试 Project Server 系统。即使您的代码正常运行，项目间的相关性、报告或其他环境因素也会导致意想不到的结果。 
    
    > [!NOTE]
    > 确保您是服务器上的有效用户，并检查您是否具有足够的权限调用您的应用程序使用的 PSI。 开发人员文档中针对每个 PSI 方法的主题均包含一个 Project Server 权限表。 例如, [QueueCreateProject](https://msdn.microsoft.com/library/WebSvcProject.Project.QueueCreateProject.aspx)方法需要全局**NewProject**权限和**SaveProjectTemplate**权限。 
  
    在某些情况中，您可能必须在服务器上执行远程调试。 您可能还需要通过在 SharePoint 场中的每台 Project server 计算机上安装事件处理程序程序集来设置事件处理程序, 然后使用 project Server Settings page in General 为 project Web App 实例配置事件处理程序。SharePoint 管理中心的应用程序设置。
    
2. **设置开发计算机。**
    
    通常，您会通过网络访问 PSI。代码示例设计为在独立于服务器的客户端上运行，除非另有说明。
    
    1. **安装正确版本的 Visual Studio。** 除非另有说明，否则将用 Visual C# 编写代码示例。 它们可用于 Visual studio 2010 或 visual studio 2012。 确保您已安装最新的 Service Pack。 
    
    2. **将 Project Server DLL 复制到开发计算机。** 将以下程序集从`[Program Files]\Microsoft Office Servers\15.0\Bin` Project Server 计算机上复制到开发计算机: 
    
       - Microsoft.Office.Project.Server.Events.Receivers.dll
    
       - Microsoft.Office.Project.Server.Library.dll
    
    3. 有关如何在 PSI 中编译 ProjectServerServices.dll 代理程序集并将其用于 WCF 服务的信息，请参阅[使用 PSI 代理程序集和 IntelliSense 说明](#pj15_PrerequisitesWCF_BuildingProxy)。
    
3. **安装 IntelliSense 文件。**
    
    若要在 project server 程序集中使用类和成员的智能感知说明, 请将更新后的智能感知 XML 文件从 project 2013 SDK 下载中复制到 project server 程序集所在的同一目录中。 例如，将 Microsoft.Office.Project.Server.Library.xml 文件复制到您的应用程序将在其中设置对 Microsoft.Office.Project.Server.Library.dll 程序集的引用的目录中。
    
    psi 服务的智能感知说明要求您使用 Project 2013 SDK 下载中的`Documentation\IntelliSense\WCF`子目录中的 CompileWCFProxyAssembly 脚本创建 psi 代理程序集。 此脚本将创建基于 WCF 的 ProjectServerServices.dll 代理程序集。 有关详细信息，请参阅 SDK 下载中的 [ReadMe_IntelliSense].mht 文件。 
    
## <a name="creating-the-application-and-adding-a-service-reference"></a>创建应用程序并添加服务引用
<a name="pj15_PrerequisitesWCF_Configure"> </a>

1. **创建控制台应用程序。**
    
    创建控制台应用程序时，请在“新建项目”**** 对话框的下拉列表中，选择“.NET Framework 4”****。可以将 PSI 示例代码复制到新的应用程序中。
    
2. **添加 WCF 所需的引用。**
    
    在解决方案资源管理器中，添加对 **System.ServiceModel** 的引用（见图 1）。 Web 应用程序将使用 **System.ServiceModel.Web**。
    
    此外，添加对 **System.Runtime.Serialization** 的引用。
    
    **图 1. 在 Visual Studio 中添加对基于 WCF 的应用程序的引用**

    ![为 WCF 添加引用](media/pj15_PrerequisitesWCF_AddReference.gif "为 WCF 添加引用")
  
3. **复制代码**。
    
    将完整的代码示例复制到控制台应用程序的 Program.cs 文件中。
    
4. **设置示例应用程序的命名空间。**
    
    您可将示例顶部列出的命名空间更改为应用程序的默认命名空间，或更改默认的应用程序命名空间以与示例匹配。可以通过更改应用程序属性来更改默认应用程序命名空间。 
    
    例如, [ReadResource](https://msdn.microsoft.com/library/WebSvcResource.Resource.ReadResource.aspx)的代码示例具有命名空间 " **CreateResourceTest**"。 如果 Visual Studio 项目的名称为**ResourceTest**, 请从 Program.cs 文件复制命名空间, 然后打开项目**属性**窗格 (在 "**项目**" 菜单上, 选择 " **ResourceTest 属性**")。 在“应用程序”**** 选项卡上，将此命名空间复制到“默认命名空间”**** 文本框中。 
    
5. **设置服务引用。**
    
    许多示例都需要对一个或多个 PSI 服务的引用。它们将在示例本身中或示例前面的注释中列出。若要获取正确的服务引用的命名空间，请确保您先设置了默认应用程序命名空间。
    
    添加 WCF 服务引用的方法有下列三种：
    
    - 生成一个名为 ProjectServerServices.dll 的 PSI 代理程序集，然后设置对该程序集的引用。请参阅[使用 PSI 代理程序集和 IntelliSense 说明](#pj15_PrerequisitesWCF_BuildingProxy)。
    
    - 将 svcutil.exe 输出中的代理文件添加到 Visual Studio 解决方案。 请参阅[添加 PSI 代理文件](#pj15_PrerequisitesWCF_AddingProxyFile)。
    
    - 使用 Visual Studio 添加服务引用。 请参阅[添加服务引用](#pj15_PrerequisitesWCF_AddingServiceReference)。
    
### <a name="using-a-psi-proxy-assembly-and-intellisense-descriptions"></a>使用 PSI 代理程序集和 IntelliSense 说明
<a name="pj15_PrerequisitesWCF_BuildingProxy"> </a>

您可将一个代理程序集用于 PSI 中的所有公共 WCF 服务。 使用 Project 2013 SDK 下载中的`Documentation\IntelliSense\WCF\CompileWCFProxyAssembly.cmd`脚本编译 projectserverservices.dll 代理程序集, 然后将代理程序集复制到开发计算机上。 将 IntelliSense 的 ProjectServerServices.xml 文件复制到同一位置。 在 Visual Studio 中，设置对 ProjectServerServices.dll 代理程序集的引用。 
  
对于 Project Server Service Pack 和更新，您可更新代理源文件并使用同一 SDK 下载文件夹中的 GenWCFProxyAssembly.cmd 脚本创建新的代理程序集。 有关指向 SDK 下载的链接, 请参阅[Project 2013 开发人员文档](project-2013-developer-documentation.md)。 有关详细信息，请参阅[添加服务引用](#pj15_PrerequisitesWCF_AddingServiceReference)部分。 
  
> [!NOTE]
> 从源 .zip 文件中提取代理源文件时, 该`Documentation\IntelliSense\WCF\Source`文件夹中的文件在项目 2013 SDK 下载的发布日期是最新的。 若要生成更新的 PSI 代理源文件，请在 Project Server 计算机上运行 GenASMXProxyAssembly.cmd 脚本。 有关详细信息，请参阅[添加服务引用](#pj15_PrerequisitesWCF_AddingServiceReference)。 
> 
> `Documentation\IntelliSense\ASMX`文件夹中的脚本对基于 WCF 的应用程序不起作用。 GenASMXProxyAssembly.cmd 脚本调用将为 ASMX 服务生成源代码文件的 Wsdl.exe。 ASMX 代理文件包括各种类和属性。 例如，基于 ASMX 的资源 Web 服务包含 **Resource** 类，而基于 WCF 的资源服务包含 **Resource** 接口、**ResourceChannel** 接口和 **ResourceClient** 类。 
  
为 ASMX Web 服务和 WCF 服务创建的任意命名空间都是相同的，以便 IntelliSense 的 ProjectServerServices.xml 文件可用于任一程序集。 例如，基于 WCF 的代理程序集和基于 ASMX 的代理程序集中的 Resource 服务的命名空间为 **SvcResource**。 当然，如果您确保命名空间名称在代理程序集和 ProjectServerServices.xml IntelliSense 文件中是匹配的，则可更改它们。
  
如果代码示例的 PSI 服务命名空间使用的名称不同，例如 **ProjectWebSvc**，若要 IntelliSense 起作用，您必须更改示例才能使用 **SvcProject**，以便命名空间与代理程序集匹配。 
  
使用基于 WCF 的代理程序集的优势如下：
  
- 您可在 Project Server 计算机之外的其他计算机上使用代理程序集开发大多数解决方案。设置独立服务引用需要在 Project Server 计算机上进行开发。
    
- 代理程序集包含所有 PSI 服务命名空间，因此您无需添加多个代理文件。
    
- 如果将 ProjectServerServices.xml 文件添加到其中设置了对 ProjectServerServices.dll 代理程序集的引用的同一目录中，则可获取 PSI 类和成员的 IntelliSense 说明。 有关详细信息, 请参阅 Project 2013 SDK 下载的`Documentation\IntelliSense`文件夹中的 [ReadMe_IntelliSense] 文件。 
    
**图 2. 将 IntelliSense 用于 Resource 服务中的方法**

![对 ReadResource 方法使用 Intellisense](media/pj15_PrerequisitesWCF_Intellisense.gif "对 ReadResource 方法使用 Intellisense")
  
使用代理程序集的缺点是，解决方案更大并且您必须使用解决方案来分发和安装代理程序集。还必须使用同位于代理程序集和 IntelliSense 文件的命名空间，除非您将脚本更改为生成代理程序集并将 ProjectServerServices.xml IntelliSense 文件更改为使用其他命名空间。
  
### <a name="adding-a-psi-proxy-file"></a>添加 PSI 代理文件
<a name="pj15_PrerequisitesWCF_AddingProxyFile"> </a>

项目 2013 SDK 下载包括由代理程序程序集的 svcutil.exe 命令生成的源文件。 源文件位于`Documentation\IntelliSense\WCF`子目录中的源 .zip 文件中。 您可以将一个或多个源文件添加到 Visual Studio 解决方案中, 而不是设置对代理程序集的引用。 例如, 若要使用 Project service 和资源服务, 请添加 wcf。Project.cs 和 wcf。Resource.cs 文件到解决方案。 
  
在 WCF 中，每个 PSI 服务中的主类都是由接口定义的，并且在客户端类中实现，以获取对成员的访问权限。 例如，**SvcProject.Resource** 接口是在 **SvcProject.ResourceClient** 类中实现的。 例如，若要将 **ResourceClient** 对象定义为名为 **resourceClient** 的类变量，请使用下列代码。 在此示例中，**SetClientEndpoints** 方法将创建一个使用 **basicHttp_Project** 终结点（其是在 app.config 文件中定义的）的 **resourceClient** 对象。 有关 app.config 文件的详细信息，请参阅[添加服务配置文件](#pj15_PrerequisitesWCF_AddConfig)部分。 
  
```cs
private static SvcResource.ResourceClient resourceClient;
. . .
private static void SetClientEndpoints()
{
  resourceClient = new SvcResource.ResourceClient("basicHttp_Resource");
  . . .
}
public void DisposeClients()
{
  resourceClient.Close();
  . . .
}
```

> [!NOTE]
> 无论您为名为 **SvcResource** 的 Project 服务引用使用 PSI 代理程序集还是添加代理文件，都将使用相同的代码创建和释放 **resourceClient** 对象。 
  
### <a name="adding-a-service-reference"></a>添加服务引用
<a name="pj15_PrerequisitesWCF_AddingServiceReference"> </a>

如果您未为 PSI 服务使用基于 WCF 的代理程序集或添加代理文件，则可直接在 Visual Studio 中设置一个或多个独立的服务引用。 您还可以使用以下过程的步骤1来创建更新后的代理文件, 以便为项目`Documentation\IntelliSense\WCF\GenWCFProxyAssembly.cmd` 2013 SDK 下载中包含的脚本做准备。 
  
> [!NOTE]
> 若要设置服务引用，您必须在 Project Server 计算机上使用 Visual Studio。建议您使用 ProjectServerServices.dll 代理程序集或添加代理源文件，而不是直接在 Visual Studio 中添加服务引用。 
  
下面的步骤演示如何使用 Visual Studio 2012 在运行 Project Server 的测试安装的计算机上设置服务引用:
  
1. 若要获取对后端 WCF 服务的访问权限，请在 Project Server 计算机上运行 Visual Studio。
    
2. 在“解决方案资源管理器”**** 中，右键单击“引用”**** 文件夹，然后选择“添加服务引用”****。 
    
3. 在 "**添加服务引用**" 对话框中的 "**地址**" 文本框中, https://localhost:32843/键入_GUID_/psi/ _ServiceName_.svc, 然后按**enter**。 将_GUID_替换为 Project Server service 应用程序的虚拟目录名称, 例如534c37eb00d74ccfadcecf9827e95239。 将_ServiceName_替换为服务名称, 例如 "资源" (参见图 3)。 
    
   您可通过下列方式之一获取 Project Server Service 虚拟目录的名称：
    
   - 在浏览器中打开 SharePoint 2013 管理中心应用程序。 选择“管理服务应用程序”****，然后选择所需的 Project Server PSI Service 应用程序。 例如，选择“ProjectServerService”****。 "管理 Project Web App 网站" 页的 URL 包含虚拟目录名称。 例如, 在中`https://ServerName:8080/_admin/pwa/managepwa.aspx?appid=534c37eb-00d7-4ccf-adce-cf9827e95239`, 虚拟目录名称为`534c37eb00d74ccfadcecf9827e95239` (目录名中不包含短划线)。 
    
   - 在 Project Server 计算机上打开“Internet Information Services (IIS) 管理器”**** 对话框。在“连接”**** 窗格的“SharePoint Web 服务”**** 节点，然后展开该节点下的服务虚拟目录，直到您发现目录包含 PSI 文件夹。选择目录，然后选择“操作”**** 窗格中的“高级设置”****，然后将目录名称复制在“虚拟路径”**** 字段中。 
    
      > [!NOTE]
      > 存在多个 Project Server Service 虚拟目录。 确保选择包含您所需的 Project Web App 实例的虚拟目录。 
  
   - 在随 SharePoint 2013 一起安装的 Windows PowerShell 中使用**SPServiceApplication** cmdlet。 在任务栏“开始”**** 菜单上，先后选择“所有程序”****、“Microsoft SharePoint 2013 产品”**** 和“SharePoint 2013 Management Shell”****。 下面是“SharePoint 2013get- Management Shell”**** 窗口中的已定义服务应用程序的命令和结果（您的 GUID 将不同）。 复制 Project Server Service Application 的 GUID。 
    
        ```powershell
            PS > get-SPServiceApplication
            DisplayName          TypeName             Id
            -----------          --------             --
            State Service        State Service        04041cfa-4ab3-4473-8bc8-3967b02eff39
            ProjectServerSer...  Project Server PS... 534c37eb-00d7-4ccf-adce-cf9827e95239
            Security Token Se... Security Token Se... 7243732e-edea-405d-8cc8-1716b99faef5
            Application Disco... Application Disco... 3bfbdeb0-bc20-4a21-801c-cc6f1ce6c643
            SharePoint Server... SharePoint Server... 09912f49-3b72-462f-a44c-6533b578286a  
        ```

      如果您知道 Project Server Service Application 的全名，则可使用它获取 GUID 值，例如：
    
        ```powershell
        PS > $projectService = "ProjectServerService"
        PS > (get-SPServiceApplication -Name $projectService).Id
        Guid
        ----
        534c37eb-00d7-4ccf-adce-cf9827e95239
       ```

      > [!NOTE]
      > 删除 GUID 中的短划线以获取虚拟目录名称。 
  
   url ( `https://localhost:32843/534c37eb00d74ccfadcecf9827e95239/PSI/Resource.svc`例如 Project Server 服务的标准 url)。 
    
4. 解析服务引用之后，在“命名空间”**** 文本框中键入引用名称。 Project 2013 开发人员文档中的代码示例使用任意命名空间名称**Svc _ServiceName_**。 例如，Resource 服务在代码示例中名为 **SvcResource**。
    
    **图 3. 添加基于 WCF 的 Resource 服务引用**

    ![添加基于 WCF 的资源服务引用](media/pj15_PrerequisitesWCF_AddSvcReference.gif "添加基于 WCF 的资源服务引用")
  
5. 将项目服务目录中的临时 web.config 文件替换为原始文件 (重命名为 web.config), 然后重新运行`iisreset`。
    
## <a name="setting-other-references"></a>设置其他引用
<a name="pj15_PrerequisitesWCF_OtherReferences"> </a>

Project Server 应用程序通常使用其他服务, 如 SharePoint 2013 web 服务。 如果需要其他服务或引用，将在代码示例中记录它们。
  
代码示例的本地引用列出在示例顶部的 **using** 语句中。 
  
1. 在“解决方案资源管理器”**** 中，右键单击“引用”**** 文件夹，然后选择“添加引用”****。
    
2. 选择“浏览”****，然后浏览到之前复制的 Project Server DLL 的存储位置。选择所需 DLL，然后选择“确定”****。
    
> [!NOTE]
> 确保您的开发计算机上的程序集版本与目标 Project Server 计算机上的程序集版本完全匹配。 
  
## <a name="adding-a-service-configuration-file"></a>添加服务配置文件
<a name="pj15_PrerequisitesWCF_AddConfig"> </a>

如果应用程序以编程方式配置 WCF 服务，则将不会使用服务配置文件。 否则, Windows 应用程序或控制台应用程序将使用 app.config 文件中的**system.servicemodel**元素;web 应用程序在 web.config 中包括**system.servicemodel** 。有关使用 app.config 文件或以编程方式配置 WCF 服务的详细信息, 请参阅[演练: 使用 WCF 开发 PSI 应用程序](https://msdn.microsoft.com/library/65707234-c3da-44e4-8364-32a6be28f645%28Office.15%29.aspx)。
  
当它生成服务代理源文件时, svcutil.exe 命令还会创建一个输出 .config 文件, 该文件是 app.config 文件或 web.config 文件中的默认**system.servicemodel**元素的基础。 Project 2013 SDK 下载在中`Documentation\IntelliSense\WCF\Source.zip`包含一个示例输出文件。 例如, svcutil.exe 为资源服务创建的默认输出 .config 文件包括名为**BasicHttpBinding_Resource**和**BasicHttpBinding_Resource1**的两个绑定。 **客户端**元素包含两个默认终结点。 一个终结点用于对端口32843上的 HTTP 地址进行安全访问, 另一个终结点用于在端口32843上进行正常访问, 如下所示: 
  
```XML
<client>
    <endpoint address="https://ServerName.domain:32843/GUID/PSI/Resource.svc/secure"
        binding="basicHttpBinding" bindingConfiguration="BasicHttpBinding_Resource"
        contract="SvcResource.Resource" name="BasicHttpBinding_Resource" />
address="https://ServerName.domain:32843/GUID/PSI/Resource.svc"
        binding="basicHttpBinding" bindingConfiguration="BasicHttpBinding_Resource1"
        contract="SvcResource.Resource" name="BasicHttpBinding_Resource1" />
</client>
```

PSI 服务配置不会使用默认绑定和终结点。Project Server 需要应用程序通过前端 ProjectServer.svc（其充当用于调用后端服务的传送器）访问 PSI 服务。若要创建 app.config 文件，请执行下列步骤：
  
1. 如果设置对 ProjectServerServices.dll 代理程序集的引用，或为服务添加代理资源文件，则应用程序将不包含 app.config 文件。 将新项目添加到 Visual Studio 项目。 在 "**添加新项**" 对话框中, 选择 "**应用程序配置文件**" 模板, 将其命名为 app.config, 然后选择 "**添加**"。
    
2. 删除 app.config 文件中的所有文本，然后将下列代码复制到文件。 例如`basicHttpConf`, 您可以为每个服务终结点使用相同的绑定。 如果要使用多个绑定，例如，若要绑定 HTTP 和 HTTPS 协议，您必须为每个协议创建一个绑定。
    
    ```XML
        <?xml version="1.0" encoding="utf-8" ?>
        <configuration>
            <system.serviceModel>
                <behaviors>
                    <endpointBehaviors>
                        <behavior name="basicHttpBehavior">
                            <clientCredentials>
                                <windows allowedImpersonationLevel="Impersonation" />
                            </clientCredentials>
                        </behavior>
                    </endpointBehaviors>
                </behaviors>
                <bindings>
                    <basicHttpBinding>
                        <binding name="basicHttpConf" sendTimeout="01:00:00" 
                            maxBufferSize="500000000" maxReceivedMessageSize="500000000">
                            <readerQuotas maxDepth="32" maxStringContentLength="8192" 
                                maxArrayLength="16384" maxBytesPerRead="4096" 
                                maxNameTableCharCount="500000000" />
                            <security mode="TransportCredentialOnly">
                                <transport clientCredentialType="Ntlm" realm="https://SecurityDomain" />
                            </security>
                        </binding>
                    </basicHttpBinding>
                </bindings>
                <client>
                    <endpoint address="https://ServerName/ProjectServerName/_vti_bin/PSI/ProjectServer.svc"
                        behaviorConfiguration="basicHttpBehavior" binding="basicHttpBinding"
                        bindingConfiguration="basicHttpConf" 
                        contract="SvcServiceName.ServiceName"
                        name="basicHttp_ServiceName" />
                </client>
            </system.serviceModel>
        </configuration>
    ```

3. 将`ServerName/ProjectServerName`客户端终结点地址替换为您的服务器和 Project Web App 实例的名称。 
    
4. 将`ServiceName`替换为 PSI 服务的名称, 例如 Resource。 确保替换服务名称的所有三个实例，例如：
    
    ```XML
        <endpoint address="https://myserver/pwa/_vti_bin/PSI/ProjectServer.svc"
            behaviorConfiguration="basicHttpBehavior" binding="basicHttpBinding"
            bindingConfiguration="basicHttpConf" 
            contract="SvcResource.Resource"
            name="basicHttp_Resource" />
    ```

5. 若要使用多个 PSI 服务，请为每个服务以及服务使用的每个 **binding** 元素创建一个 **endpoint** 元素。 例如，下列终结点将客户端配置为对 Project 服务和 QueueSystem 服务使用 HTTP 绑定。 
    
    > [!NOTE]
    > 如果运行应用程序时收到“服务器太忙”或“HTTP 请求未经授权”的错误，请确保 app.config 文件中的终结点地址正确。 
  
    ```XML
        <client>
        <endpoint address="https://ServerName/pwa/_vti_bin/PSI/ProjectServer.svc"
            behaviorConfiguration="basicHttpBehavior" binding="basicHttpBinding"
            bindingConfiguration="basicHttpConf" 
            contract="SvcProject.Project"
            name="basicHttp_Project" />
        <endpoint address="https://ServerName/pwa/_vti_bin/PSI/ProjectServer.svc"
            behaviorConfiguration="basicHttpBehavior" binding="basicHttpBinding"
            bindingConfiguration="basicHttpConf" 
            contract="SvcQueueSystem.QueueSystem"
            name="basicHttp_QueueSystem" />
        </client>
    ```

您可使用 Visual Studio 中的“WCF 服务配置编辑器”**** 编辑 app.config 文件（位于“工具”**** 菜单上）。 图4显示了如何在 " **Microsoft 服务配置编辑器**" 对话框中设置**contract**元素。 如果解决方案使用的是 PSI 代理程序集, 则在 Visual Studio 解决方案的`bin\debug`目录中打开 projectserverservices.dll。 “合同类型浏览器”**** 对话框将显示所有 WCF 服务联系人（见图 5）。 
  
**图 4. 使用 WCF 服务配置编辑器**

![使用 WCF 服务配置编辑器](media/pj15_PrerequisitesWCF_ServiceConfigurationEditor.gif "使用 WCF 服务配置编辑器")
  
如果解决方案使用的是服务代理文件 (如 wcfResource.cs), 则编译该应用程序, 然后在`bin\debug`目录中打开该可执行文件。 有关编辑 app.config 文件的详细信息，请参阅[演练：使用 WCF 开发 PSI 应用程序](https://msdn.microsoft.com/library/65707234-c3da-44e4-8364-32a6be28f645%28Office.15%29.aspx)。
  
**图 5. 使用 WCF 服务配置编辑器中的合同类型浏览器**

![使用合同类型浏览器](media/pj15_PrerequisitesWCF_ContractTypeBrowser.gif "使用合同类型浏览器")
  
## <a name="using-multiple-authentication"></a>使用多身份验证
<a name="pj15_PrerequisitesWCF_ClaimsMultiAuth"> </a>

Project Server 用户的身份验证，无论是通过 Windows 身份验证还是表单身份验证，均是通过 SharePoint 中的声明处理完成的。 多身份验证意味着, 在其上预配 Project web App 的 web 应用程序支持 Windows 身份验证和基于表单的身份验证。 如果属于这种情况，则对使用 Windows 身份验证的 WCF 服务的任何调用将因以下错误失败，因为声明处理无法确定要进行身份验证的用户类型：
  
`The server was unable to process the request due to an internal error. For more information about the error, either turn on Include ExceptionDetailInFaults (either from ServiceBehaviorAttribute or from the <serviceDebug> configuration behavior) on the server in order to send the exception information back to the client, or turn on tracing as per the Microsoft .NET Framework 3.0 SDK documentation and inspect the server trace logs.`

若要修复此 WCF 问题，对 PSI 方法的任何调用因位于为每个 PSI 服务定义的 **OperationContextScope** 中。 请勿嵌套多个服务的域；例如，对 Resource 服务和 Project 服务使用调用时，每组呼叫应位于其自己的域中。 
  
在以下示例中，**DisableFormsAuth** 方法可通过应用程序中的每个 **OperationContextScope** 部分进行调用。 该方法将删除任何以前禁用的窗体身份验证的头值, 以便在_isWindowsAuth_参数为**false**时可以继续进行表单身份验证。 如果_isWindowsAuth_为**true**, 则**DisableFormsAuth**方法将禁用表单身份验证。 
  
在 **WcfSample** 方法中，**projectClient** 对象是 PSI **SvcProject.ProjectClient** 类的一个实例。 
  
```cs
// Class variable that determines whether to disable Forms authentication.
private bool isWindowsUser = true;
public void DisableFormsAuth(bool isWindowsAuth)
{
    WebOperationContext.Current.OutgoingRequest.Headers.Remove(
        "X-FORMS_BASED_AUTH_ACCEPTED");
    if (isWindowsAuth)
    {
        // Disable Forms authentication, to enable Windows authentication.
        WebOperationContext.Current.OutgoingRequest.Headers.Add(
            "X-FORMS_BASED_AUTH_ACCEPTED", "f");
    }
}
private void WcfSample()
{
    // Limit the scope of WCF calls to the client channel. 
    using (OperationContextScope scope = new OperationContextScope(projectClient.InnerChannel))
    {
        // Add a web request header to enable Windows authentication in 
        // multiple authentication installations.
        DisableFormsAuth(isWindowsUser);
        // Add calls to the projectClient methods here:
        // . . .
    }
}
```

> [!NOTE]
> 在 **OperationContextScope** 中调用 PSI 只需在多身份验证环境中运行的应用程序。 如果 Project Server 仅使用 Windows 身份验证，则无需设置域和添加禁用表单身份验证的 Web 请求头。 
> 
> 对于基于 ASMX 的应用程序的修复则不同。 有关详细信息, 请参阅 Project 中的[针对基于 .asmx 的代码示例的先决条件](prerequisites-for-asmx-based-code-samples-in-project.md)中的 "*使用多重身份验证*" 部分。 
  
## <a name="changing-values-of-generic-constants"></a>更改泛型常量值
<a name="pj15_PrerequisitesWCF_ChangeValues"> </a>

大多数示例都包含一个或多个变量，为了让示例在您的环境中正常工作，您必须更新这些变量。 在下面的示例中，如果已安装 SSL，请使用 HTTPS 协议而不是 HTTP 协议。 将_ServerName_替换为您正在使用的服务器的名称。 将_ProjectServerName_替换为 project server 网站的虚拟目录名称, 如 PWA。 
  
```cs
const string PROJECT_SERVER_URI = "https://ServerName/ProjectServerName/";
```

代码示例顶部记录了必须更改的其他变量。
  
## <a name="verifying-the-results"></a>验证结果
<a name="pj15_PrerequisitesWCF_Verify"> </a>

从代码示例中获取并解释结果并不总是一项简单的工作。 例如, 如果您创建一个项目, 则必须发布该项目, 然后它才能显示在 project Web App 中的 "项目中心" 页上。
  
可以通过多种方式验证代码示例结果，例如：
  
- 使用 project Professional 2013 客户端从 project Server 计算机打开项目, 并查看所需的项目。
    
- 在 project Web App 的 "项目中心" 页上查看已`https://ServerName/ProjectServerName/projects.aspx`发布的项目 ()。
    
- 在 Project Web App 中查看队列日志。 打开 "服务器设置" 页 (选择右上角的 "**设置**" 图标), 然后选择 "**个人设置**" 部分下的`https://ServerName/ProjectServerName/MyJobs.aspx` **"我的排队作业**" ()。 在“视图”**** 下拉列表中，可以按作业的状态进行排序。 默认状态为“上周进行中的以及失败的作业”****。 
    
- 使用 Project Web App ( `https://ServerName/ProjectServerName/_layouts/15/pwa/admin/admin.aspx`) 中的 "服务器设置" 页来管理所有队列作业, 并删除或强制签入企业对象。 您必须具有管理权限才能访问“服务器设置”页上的这些链接。
    
- 使用“Microsoft SQL Server Management Studio”**** 运行针对 Project Server 数据库的表的查询。例如，使用以下查询选择 MSP_WORKFLOW_STAGE_PDPS 表的前 200 行来显示有关工作流容器中项目详细信息页 (PDP) 的信息。 
    
```sql
        SELECT TOP 200 [STAGE_UID]
                ,[PDP_UID]
                ,[PDP_NAME]
                ,[PDP_POSITION]
                ,[PDP_ID]
                ,[PDP_STAGE_DESCRIPTION]
                ,[PDP_REQUIRES_ATTENTION]
        FROM [ProjectService].[pub].[MSP_WORKFLOW_STAGE_PDPS]
```

## <a name="cleaning-up"></a>清理
<a name="pj15_PrerequisitesWCF_Cleanup"> </a>

测试一些代码示例之后，有一些企业对象和设置应进行删除或重置。 您可以使用 Project Web App 中的 "服务器设置" 页来管理企业`https://ServerName/ProjectServerName/_layouts/15/pwa/admin/admin.aspx`数据 ()。 利用“服务器设置”页上的链接，您可以删除旧项目、强制签入项目、管理所有用户的作业队列和执行其他管理任务。
  
下面是“服务器设置”页上的部分链接，可用于在运行代码示例之后进行常规清理活动：
  
- **企业自定义域和查阅表格**
    
- **管理队列作业**
    
- **删除企业对象**
    
- **强制签入企业对象**
    
- **企业项目类型**
    
- **工作流阶段**
    
- **工作流容器**
    
- **项目详细信息页**
    
- **时间报告阶段**
    
- **时间表设置和默认值**
    
- **行分类**
    
其他设置由 SharePoint Server 2013 针对每个 project web app 实例进行管理, 而不是由特定的 Project web app Server "设置" 页进行管理。 在 SharePoint 管理中心应用程序中, 选择 "**常规应用程序设置**", 在 " **Project Server settings**" 下选择 "**管理**", 然后在 "服务器设置" 页上的下拉列表中选择 "Project Web App 实例"。. 例如, 选择 "**服务器端事件处理程序**" 以添加或删除所选 Project Web App 实例的事件处理程序。 
  
## <a name="see-also"></a>另请参阅

- [Project 中基于 ASMX 的代码示例的先决条件](prerequisites-for-asmx-based-code-samples-in-project.md)   
- [演练：使用 WCF 开发 PSI 应用程序](https://msdn.microsoft.com/library/65707234-c3da-44e4-8364-32a6be28f645%28Office.15%29.aspx)   
- [对 WCF 使用模拟](https://msdn.microsoft.com/library/e3597901-2f02-44a2-8076-d32aae540b38%28Office.15%29.aspx)  
- [Project PSI 参考概述](project-psi-reference-overview.md) 
- [SharePoint 开发中心](https://msdn.microsoft.com/sharepoint/default.aspx)
    

