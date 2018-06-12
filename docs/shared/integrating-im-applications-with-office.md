---
title: 与 Office 集成 IM 应用程序
manager: soliver
ms.date: 07/25/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: beba316b-1dfe-4e1b-adae-42418906c177
description: 本文介绍如何配置即时消息 (IM) 客户端应用程序，使其与 Office 2013，包括显示状态和发送即时消息从联系人卡片中的社会功能集成。
ms.openlocfilehash: 383aac24be347cf637d9e2f255623035eea8bc40
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779568"
---
# <a name="integrating-im-applications-with-office"></a>与 Office 集成 IM 应用程序

本文介绍如何配置即时消息 (IM) 客户端应用程序，使其与 Office 2013，包括显示状态和发送即时消息从联系人卡片中的社会功能集成。
  
如果您有任何问题或意见本技术文章或该描述的过程，您可以与 Microsoft 联系直接通过向[docthis@microsoft.com](mailto:docthis@microsoft.com)发送电子邮件。
  
## <a name="introduction"></a>简介
<a name="off15_IMIntegration_Intro"> </a>

Office 2013 提供了丰富集成 IM 客户端应用程序，包括 Lync 2013。 这种集成在 SharePoint 2013 页面上为用户提供从 Word 2013、 Excel 2013、 PowerPoint 2013、 Outlook 2013、 Visio 2013、 Project 2013 和 OneNote 2013 中的 IM 功能，以及提供状态集成。 用户可以看到照片、 名称、 的状态，以及在其联系人列表中人员的联系人数据。 它们可以直接从联系人卡片 （某联系人信息和通信选项的 Office 2013 中的用户界面元素） 开始 IM 会话、 视频呼叫或电话呼叫。 Office 2013 更加方便而不用您让您的电子邮件或文档之外保持连接到您的联系人。 
  
> [!NOTE]
> 本文使用术语 IM 客户端应用程序来明确引用将传达至 IM 服务的用户的计算机上安装的应用程序。 例如，Lync 2013 被视为 IM 客户端应用程序。 本文不提供有关如何 IM 客户端应用程序将传达至 IM 服务或 IM 服务本身详细信息。 
  
可以自定义 IM 客户端应用程序，以便它使用 Office 进行通信。 具体而言，您可以修改 IM 应用程序，以使其显示在 Office ui 的以下信息：
  
- 联系人的照片。
    
- 联系人姓名。
    
- 联系人的个人状态注释。
    
- 联系人状态。
    
- 联系人可用性字符串 （例如，"有空"或"外出"）。
    
- 联系人功能字符串 （例如，"视频就绪"）。
    
- 一次单击 IM 启动。
    
- 一次单击视频呼叫启动。
    
- 一键式电话呼叫启动 （包括 SIP、 电话号码、 语音邮件和呼叫新号码）。
    
- 联系人管理 （将添加到 IM 组）。
    
- 联系人位置和时区。
    
- 联系人数据、 电话号码、 电子邮件地址、 标题和公司名称。
    
**图 1。Office 2013 中的联系人卡片**

![Office 2013 中的人员卡片](media/ocom15_peoplecard.png "Office 2013 中的人员卡片")
  
若要启用此与 Office 的集成，IM 客户端应用程序必须实现一组 Office 提供连接到它的接口。 这种集成的 Api 都包含在 Microsoft.Office.UC.dll 文件，其中包括 Lync 的版本的 Office 2013 安装中包含的[UCCollborationLib](http://msdn.microsoft.com/en-au/library/uccollaborationlib.aspx)命名空间 / for Business 的 Skype。 **UCCollaborationLib**命名空间包含与 Office 集成时必须实现的接口。 
  
> [!IMPORTANT] 
> Lync 2013/Skype for Business 中嵌入所需的接口的类型库。 为第三方集成商它仅当在目标计算机上安装 Lync 2013 和 Skype for Business 时。 如果要使用标准 Office 集成，您需要提取类型库在目标计算机上安装它。 [Lync 2013 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=36824)包含 Microsoft.Office.UC.dll 文件。 
  
> [!NOTE]
>  少量的 Office 2010 应用程序可以与第三方 IM 提供程序应用程序以类似方式集成： Outlook 2010、 Word 2010、 在 Excel 2010、 PowerPoint 2010 和 SharePoint Server 2010 （使用 ActiveX 控件）。 使用 Office 2013 的集成所需的步骤的许多也适用于 Office 2010。 有多个 Office 2010 如何集成使用 IM 提供程序应用程序中的主要区别： 
>  - Office 2010 不显示联系人的照片。 
>  - 从 Office 2010 中，必须单独下载 Microsoft.Office.Uc.dll 文件。 [Lync 2010 SDK](http://www.microsoft.com/en-us/download/details.aspx?id=18898)包含用于 Office 2010 的 Microsoft.Office.UC.dll 文件。 
>  - 当 Office 应用程序上的 IM 客户端应用程序调用[IUCOfficeIntegration.GetAuthenticationInfo](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IUCOfficeIntegration)方法时，它将传递字符串"14.0.0.0"中。 
>  - Office 2010 枚举所有组和联系人，只要连接到 IM 客户端应用程序。 
  
## <a name="how-office-integrates-with-an-im-client-application"></a>Office 如何与 IM 客户端应用程序集成
<a name="off15_IMIntegration_How"> </a>

Office 2013 应用程序启动时，它会通过下面的过程可以与默认 IM 客户端应用程序集成：
  
1. 它将检查注册表以发现默认 IM 客户端应用程序，然后连接到它。
    
2. 它通过 IM 客户端应用程序的身份验证。
    
3. 连接到特定由 IM 客户端应用程序公开的接口。
    
4. 它确定当前已登录的用户 （本地用户），包括获取用户的联系人，确定用户的状态，以及确定用户的 IM 功能 （即时消息、 视频聊天、 VOIP，等） 的功能。
    
5. 它获取本地用户的联系人的状态信息。
    
6. IM 客户端应用程序关闭时，Office 2013 应用程序以无提示方式断开连接。
    
### <a name="discovering-the-im-application"></a>发现 IM 应用程序

Office 应用程序查找多个特定的键和发现的默认 IM 客户端应用程序注册表中条目。 如果发现时的默认 IM 客户端应用程序，然后尝试连接到它。
  
Office 应用程序经过发现默认 IM 客户端应用程序的过程如下所示：
  
1. Office 应用程序查找要 HKEY_CURRENT_USER\Software\IM Providers\DefaultIMApp 将注册表子项中的是否已设置并读取应用程序名称列出。
    
2. Office 应用程序然后读取 HKEY_CURRENT_USER\Software\IM Providers\_应用程序名称_\UpAndRunning 密钥并监视更改的值。
    
3. 接下来，Office 应用程序读取 HKEY_LOCAL_MACHINE\Software\IM Providers\_应用程序名称_注册表项，并获取那里存储的 ProcessName 和类 ID (CLSID) 值。 
    
4. IM 客户端应用程序已成功完成其开始序列并注册的所有正确的状态集成类后，将"2"的 HKEY_CURRENT_USER\Software\IM Providers\_应用程序名称_\UpAndRunning 关键指示客户端应用程序正在运行。
    
5. 当 Office 应用程序发现 HKEY_CURRENT_USER\Software\IM Providers\_应用程序名称_\UpAndRunning 密钥已被设置为"2"时，它会检查 IM 客户端应用程序的过程名称的计算机上运行进程的列表。
    
6. 一旦在 Office 应用程序发现 IM 客户端应用程序使用的过程，Office 应用程序调用**CoCreateInstance**使用 CLSID 建立到为进程外 COM 服务器的 IM 客户端应用程序的连接。 
    
### <a name="authenticating-the-connection-to-the-im-application"></a>身份验证与 IM 应用程序的连接

Office 应用程序建立到 IM 客户端应用程序的连接后，它然后执行以下操作：
  
1. Office 应用程序调用[IUnknown::QueryInterface](http://msdn.microsoft.com/en-us/library/ms682521%28v=VS.85%29.aspx)方法来检查[IUCOfficeIntegration](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IUCOfficeIntegration)接口。 
    
2. Office 应用程序然后调用**IUCOfficeIntegration.GetAuthenticationInfo**方法，传递中最高的支持的集成版本 (例如，"15.0.0.0")。 
    
3. 如果 IM 客户端应用程序支持的 Office 中作为参数传递的版本，应用程序将返回到调用代码的下面的硬编码 XML 字符串：
    
    `<authenticationinfo>`
    
   > [!NOTE]
   > 出于旧版 IM 客户端应用程序必须返回的确切值`<authenticationinfo>`对**GetAuthenticationInfo**调用如果它所支持的版本 Office 中作为参数传递。 
  
4. 如果 IM 客户端应用程序未能返回一个值，Office 应用程序调用**GetAuthenticationInfo**再次具有最高支持下一版本的 Office (例如，"14.0.0.0")。 
    
5. 一旦 Office 确定 IM 客户端应用程序支持 IM 和状态集成，则它将连接到一所需的接口，若要完成初始化。 （有关详细信息，请参阅[Connecting to 所需的接口](#off15_IMIntegration_HowConnect)）。
    
如果 Office 应用程序遇到的上述步骤任何错误，它退出并重新在 Office 应用程序会话期间未建立状态集成。 
  
### <a name="connecting-to-required-interfaces"></a>连接到所需的接口
<a name="off15_IMIntegration_HowConnect"> </a>

身份验证后与 IM 客户端应用程序的连接，Office 应用程序尝试连接到一组 IM 客户端应用程序必须公开的所需的接口。 Office 应用程序可通过执行以下操作：
  
- Office 应用程序获取[ILyncClient](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ILyncClient)对象通过调用**IUCOfficeIntegration.GetInterface**方法，并在**oiInterfaceLyncClient**传递常量[UCCollaborationLib.OIInterface](http://msdn.microsoft.com/library/UCCollaborationLib.OIInterface)枚举中。 
    
- Office 应用程序获取[IAutomation](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IAutomation)对象通过调用**IUCOfficeIntegration.GetInterface**方法，并在**oiInterfaceAutomation**传递常量**OIInterface**枚举中。 
    
- Office 应用程序设置[_ILyncClientEvents](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ILyncClient)事件侦听器。 
    
- Office 应用程序设置[_IUCOfficeIntegrationEvents](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IUCOfficeIntegration)事件侦听器。 
    
- Office 应用程序通过访问**ILyncClient.State**属性，从 IM 客户端应用程序中获取的登录状态。 
    
- Office 应用程序通过调用[UCCollaborationLib.OIFeature](http://msdn.microsoft.com/library/UCCollaborationLib.OIFeature)枚举中返回一个标志**IUCOfficeIntegration.GetSupportedFeatures**方法获取 IM 客户端应用程序的功能。 
    
- Office 应用程序访问**ILyncClient.Self**属性来获取对[ISelf](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ISelf)对象的引用。 
    
### <a name="retrieving-the-capabilities-of-the-local-user"></a>检索本地用户的功能
<a name="off15_IMIntegration_HowConnect"> </a>

Office 应用程序获取本地用户的功能，通过执行以下操作：
  
1. 如果 IM 客户端应用程序支持**IClient2**接口，Office 将尝试通过访问**IClient2.PrivateContactManager**属性获取[IContactManager](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactManager)对象。 
    
2. 如果 IM 应用程序不支持**IClient2**接口，Office 应用程序通过访问**ILyncClient.ContactManager**属性获取**IContactManager**对象。 在建立任何其他即时消息功能前，IM 客户端应用程序必须成功返回**IContactManager**对象。 
    
3. Office 应用程序访问**ILyncClient.Uri**属性，然后调用**IContactManager.GetContactByUri**获取与本地用户关联的[IContact](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContact)对象。 
    
4. Office 应用程序然后调用几个**IContact.CanStart**来建立**ModalityTypes.ucModalityInstantMessage**和**ModalityTypes.ucModalityAudioVideo**传入值的本地用户的功能连续。 
    
### <a name="retrieving-contact-presence"></a>检索联系人的状态
<a name="off15_IMIntegration_HowConnect"> </a>

Office 应用程序获取联系人的状态，包括本地用户，通过执行以下操作： 
  
1. 在 Office 应用程序调用**IContact.GetContactInformation**若要从联系人中获取的状态项。 
    
2. 从联系人，然后在 Office 应用程序订阅更改状态。 它调用**IContactManager.CreateSubscription**获取[IContactSubscription](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactSubscription)对象。 它然后调用**IContactSubscription.AddContact**将联系人添加到订阅，然后调用**IContactSubscription.Subscribe**以获取联系人的状态中的更改。 
    
3. 如果 IM 应用程序支持**IContact2**，Office 将尝试通过调用**IContact2.BatchGetContactInformation2**获取状态信息。
    
4. Office 应用程序然后调用**IContact.BatchGetContactInformation**来检索该联系人的状态属性。 Office 应用程序可以通过访问**IContact.Settings**属性获取第二个一整套状态属性。 
    
5. 最后，Office 应用程序通过访问**IContact.CustomGroups**属性获取联系人的组成员身份。 这将返回一个[IGroupCollection](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IGroup)集合，该集合包含的所有联系人都属于[IGroup](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IGroup)对象。 
    
### <a name="disconnecting-from-the-im-application"></a>断开 IM 应用程序
<a name="off15_IMIntegration_HowConnect"> </a>

当 Office 2013 应用程序检测到的来自 IM 应用程序的**OnShuttingDown**事件时，则它以无提示方式断开连接。 但是，如果在 Office 应用程序关闭前的 IM 应用程序时，Office 应用程序，不保证清理连接。 IM 应用程序必须处理客户端连接泄漏。 
  
## <a name="setting-registry-keys-and-entries"></a>设置注册表项和条目
<a name="off15_IMIntegration_SetRegistry"> </a>

如前所述，支持 IM 的 Office 2013 应用程序查找特定键、 项和注册表来发现要连接到的 IM 客户端应用程序中的值。 这些注册表值提供 Office 应用程序的过程名称和充当 IM 客户端应用程序的对象模型 （实现**IUCOfficeIntegration**接口的类） 的入口点类的 CLSID。 Office 应用程序共同创建的类，并为进程外 COM 服务器 IM 客户端应用程序中的客户端连接。 
  
表 1 用于标识键、 项和必须用注册表以与 Office 集成 IM 客户端应用程序编写的值。
  
**表 1。注册表项设置默认 IM 客户端应用程序**

|**注册表项**|**项**|**类型**|**值**|**示例**|
|:-----|:-----|:-----|:-----|:-----|
|HKEY_LOCAL_MACHINE\Software\IM 提供程序\\< 应用程序名称\>  <br/> |FriendlyName  <br/> |REG_SZ  <br/> |第三方 IM 客户端应用程序的名称。  <br/> |Litware IM 2012  <br/> |
||ProcessName  <br/> |REG_SZ  <br/> |第三方 IM 客户端应用程序的过程名称。  <br/> |litware.exe  <br/> |
||GUID  <br/> |REG_SZ  <br/> |用于根目录中，IM 应用程序 （实现**IUCOfficeIntegration**接口的类） 中的 cocreatable 类的类 ID (CLSID)。  <br/> |(GUID)  <br/> |
|HKEY_CURRENT_USER\Software\IM 提供程序  <br/> |DefaultIMApp  <br/> |REG_SZ  <br/> |IM 客户端应用程序的名称。 这必须是在 HKEY_LOCAL_MACHINE 中的顶级的注册表项 （配置单元） 的名称相同。  <br/> |Litware  <br/> |
|HKEY_CURRENT_USER\Software\IM 提供程序\\< 应用程序名称\>  <br/> |UpAndRunning  <br/> |REG_DWORD  <br/> | 0 和 2 之间的整数值：  <br/>  0-不运行  <br/>  1 — 启动  <br/>  2 — 运行  <br/> <br/>**注意**： 应用程序名称注册表项必须 DefaultIMApp 条目的值相同。           ||
   
## <a name="implementing-the-required-interfaces-for-integration-with-office"></a>实现与 Office 集成所需的接口
<a name="off15_IMIntegration_ImplementRequired"> </a>

有三个接口从 IM 客户端应用程序的可执行文件 （或 COM 服务器） 必须实现以便它可以与 Office 集成**UCCollaborationLib**命名空间。 如果未实现这些接口，Office 应用程序在初始化过程中退出和未建立与 IM 客户端应用程序的连接。 
  
所需的接口，如下所示：
  
- [IUCOfficeIntegration](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IUCOfficeIntegration)— 虽然不要求，在 **_IUCOfficeIntegrationEvents**接口，还应在相同的派生类中实现。 
    
- [ILyncClient](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ILyncClient)— 虽然不要求，在 **_ILyncClientEvents**接口，还应在相同的派生类中实现。 
    
- [IAutomation](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IAutomation)
    
### <a name="iucofficeintegration-interface"></a>IUCOfficeIntegration 接口
<a name="off15_IMIntegration_ImplementRequired_IUCOfficeIntegration"> </a>

**IUCOfficeIntegration**接口提供了 Office 应用程序连接到 IM 客户端应用程序的入口点。 该接口定义的启动与 IM 客户端应用程序的连接过程的一部分调用 Office 应用程序的三种方法。 必须共同可创建实现**IUCOfficeIntegration**接口的类，以便 Office 可以共同创建它的一个实例。 此外，它必须公开 HKEY_LOCAL_MACHINE\Software\IM Providers\_应用程序名称_注册表项中的 GUID 项输入值的 CLSID。 
  
继承自**IUCOfficeIntegration**类还应实现 **_IUCOfficeIntegrationEvents**接口。 **_IUCOfficeIntegrationEvents**接口包含公开**IUCOfficeIntegration**接口的事件处理程序的成员。 
  
表 2 显示了必须继承自**IUCOfficeIntegration**和 **_IUCOfficeIntegration**类中实现的成员。
  
> [!NOTE]
> 有关**IUCOfficeIntegration** **_IUCOfficeIntegrationEvents**接口和其成员的详细信息，请参阅[UCCollaborationLib.IUCOfficeIntegration](http://msdn.microsoft.com/library/UCCollaborationLib.IUCOfficeIntegration)和[UCCollaborationLib._IUCOfficeIntegrationEvents](http://msdn.microsoft.com/library/UCCollaborationLib._IUCOfficeIntegrationEvents). 
  
**表 2。IUCOfficeIntegration 和 _IUCOfficeIntegrationEvents 接口实现**

|**接口**|**成员**|**说明**|
|:-----|:-----|:-----|
|**IUCOfficeIntegration** <br/> |**GetAuthenticationInfo**方法  <br/> |获取身份验证信息字符串。  <br/> |
||**GetInterface**方法  <br/> |获取特定版本的接口。  <br/> |
||**GetSupportedFeatures**方法  <br/> |获取的受支持的 Office 集成功能。  <br/> |
|**_IUCOfficeIntegrationEvents** <br/> |**OnShuttingDown**事件  <br/> |IM 客户端应用程序尝试关闭时引发的事件。  <br/> |
   
使用以下代码定义继承 IM 客户端应用程序中的**IUCOfficeIntegration**和 **_IUCOfficeIntegration**接口的类。 
  
```cs
// An example of a class that can be co-created and can integrate
// with Office as an IM provider.
[ClassInterface(ClassInterfaceType.None)]
[ComSourceInterfaces(typeof(_IUCOfficeIntegrationEvents))]
[Guid("{CLSID value}"), ComVisible(true)]
public class LitwareClientAppObject : IUCOfficeIntegration
{
    // Implementation details omitted.
}

```

**GetAuthenticationInfo**方法采用作为_版本_参数的参数字符串。 Office 应用程序调用此方法时，它将传递两个字符串之一的参数，具体取决于 Office 的版本。 Office 应用程序时提供的 IM 客户端应用程序支持的 Office 版本的方法 （即，支持功能） 的**GetAuthenticationInfo**方法返回一个硬编码的 XML 字符串`<authenticationinfo>`。 
  
使用以下代码实现 IM 客户端应用程序代码中的**GetAuthentication**方法。 
  
```cs
public string GetAuthenticationInfo(string _version)
{
    // Define the version of Office that the IM client application supports.
    string supportedOfficeVersion = "15.0.0.0";
    // Do a simple check for equivalency.
    if (supportedOfficeVersion == _version)
    {
        // If the version of Office is supported, this method must 
        // return the string literal "<authenticationinfo>" exactly.
        return "<authenticationinfo>";
    }
    else
    {
        return null;
    }
}

```

**GetInterface**方法调用的代码中，具体取决于什么作为的_界面_参数作为参数传入到 shuttles 类的引用。 Office 应用程序调用**GetInterface**方法时，它中传递两个值之一接口参数： **oiInterfaceILyncClient**常量 （1） 或 （2） 的[**oiInterfaceIAutomation**常量UCCollaborationLib.OIInterface](http://msdn.microsoft.com/library/UCCollaborationLib.OIInterface)枚举。 如果在 Office 应用程序通过**oiInterfaceILyncClient**常量， **GetInterface**方法将返回对实现**ILyncClient**接口的类的引用。 如果在 Office 应用程序通过**oiInterfaceIAutomation**常量，该**GetInterface**方法将返回实现**IAutomation**接口的类。 
  
使用下面的代码示例来实现 IM 客户端应用程序代码中的**GetInterface**方法。 
  
```cs
public object GetInterface(string _version, OIInterface _interface)
{
    // These objects implement the ILyncClient or IAutomation 
    // interfaces respectively. There is no restriction on what these
    // classes are named.
    IMClient imClient = new IMClient();
    IMClientAutomation imAutomation = new IMClientAutomation();
    // Return different object references depending on the value passed in
    // for the _interface parameter.
    switch (_interface)
    {
        // The calling code is asking for an object that inherits
        // from ILyncClient, so it returns such an object.
        case OIInterface.oiInterfaceILyncClient:
        {
            return imClient;
        }
        // The calling code is asking for an object that inherits
        // from IAutomation, so it returns such an object.
        case OIInterface.oiInterfaceIAutomation:
        {
            return imAutomation;
        }
        default:
        {
            throw new NotImplementedException();
        }
    }
}

```

**GetSupportedFeatures**方法返回有关 IM 客户端应用程序支持的 IM 功能的信息。 计其唯一参数，_版本_的字符串。 Office 应用程序调用**GetSupportFeatures**方法时，该方法将返回[UCCollaborationLib.OIFeature](http://msdn.microsoft.com/library/UCCollaborationLib.OIFeature)枚举中的一个值。 返回的值指定的 IM 客户端应用程序的每个功能对 Office 应用程序指示通过将一个标志添加到值的 IM 客户端的功能。 
  
> [!NOTE]
>  Office 2013 应用程序忽略**OIFeature**枚举中的以下常量： 
> - **oiFeaturePictures**(2) 
> - **oiFeatureFreeBusyIntegration**
> - **oiFeaturePhoneNormalization**
  
使用下面的代码示例来实现 IM 客户端应用程序代码中的**GetSupportFeatures**方法。 
  
```cs
public OIFeature GetSupportedFeatures(string _version)
{
    OIFeature supportedFeature1 = OIFeature.oiFeatureQuickContacts;
    OIFeature supportedFeature2 = OIFeature.oiFeatureFastSearch;
    return (supportedFeature1 | supportedFeature2);
}

```

### <a name="ilyncclient-interface"></a>ILyncClient 接口
<a name="off15_IMIntegration_ImplementRequired_ILyncClient"> </a>

**ILyncClient**接口将映射到在即时消息客户端应用程序自身的功能。 它公开本地用户和其他几个设置登录到的应用程序 （本地用户，由[UCCollaborationLib.ISelf](http://msdn.microsoft.com/library/UCCollaborationLib.ISelf)接口） 的应用程序的状态、 联系人列表中的人员所引用的属性。 时正在尝试连接到 IM 客户端应用程序，Office 应用程序获取对实现**ILyncClient**接口的对象的引用。 从该参考中，可以访问 Office 何种 IM 客户端应用程序的功能。 
  
此外，实现**ILyncClient**接口的类还应实现 **_ILyncClientEvents**接口。 **_ILyncClientEvents**接口将公开几个所需的监控 IM 客户端应用程序的状态的事件。 
  
表 3 显示了必须继承自**ILyncClient**和 **_ILyncClientEvents**类中实现的成员。
  
> [!NOTE]
> **ILyncClient**的任何成员或**\_ILyncClientEvents**表中未列出的接口必须存在但不需要实现。 已存在，但未实现的成员可以引发**NotImplementedException**或**E\_NOTIMPL**错误。 
> 
> 有关**ILyncClient** **_ILyncClientEvents**接口和其成员的详细信息，请参阅[UCCollaborationLib.ILyncClient](http://msdn.microsoft.com/library/UCCollaborationLib.ILyncClient)和[UCCollaborationLib._ILyncClientEvents](http://msdn.microsoft.com/library/UCCollaborationLib._ILyncClientEvents)。 
  
**表 3。ILyncClient 和 ILyncClientEvents 接口实现。**

|**接口**|**成员**|**说明**|
|:-----|:-----|:-----|
|**ILyncClient** <br/> |**ContactManager**属性  <br/> |获取联系人组管理器。  <br/> |
||**ConversationManager**属性  <br/> |获取对话管理器。  <br/> |
||**自我**属性  <br/> |获取的**自我**对象。  <br/> |
||**登录**方法  <br/> |启动 IM 客户端应用程序登录过程具有特定的可用性。  <br/> |
||**State**属性  <br/> |获取当前平台状态。  <br/> |
||**Uri** 属性  <br/> |获取 IM 客户端应用程序的 URI。  <br/> |
|**_ILyncClientEvents** <br/> |**OnStateChanged**事件  <br/> |IM 客户端应用程序状态更改时引发。 您应处理此事件，并获取**eventData.NewState**属性。 当应用程序中的任何子系统导致状态更改时，绑定到 IM 客户端应用程序实例的所有进程引发该事件。  <br/> |
   
在初始化过程中，Office 访问**ILyncClient.State**属性。 此属性需要从[UCCollaborationLib.ClientState](http://msdn.microsoft.com/library/UCCollaborationLib.ClientState)枚举返回一个值。 
  
```cs
private ClientState _clientState;
public ClientState State
{
    get
    {
        return this._clientState;
    }
}

```

**State**属性存储 IM 客户端应用程序的当前状态。 必须设置并更新整个 IM 客户端应用程序会话。 当 IM 客户端应用程序登录，则注销，或关闭时，应设置的**状态**属性。 它是最佳内**ILyncClient.SignIn**和**ILyncClient.SignOut**方法，此属性设置，如下面的示例演示。 
  
```cs
// This field is of a type that implements the 
// IAsynchronousOperation interface.
private IMClientAsyncOperation _asyncOperation = new IMClientAsyncOperation();
// This field is of a type that implements the ISelf interface.
private IMClientSelf _self;
public IMClientAsyncOperation SignIn(string _userUri, string _domainAndUser, 
    string _password, object _IMClientCallback, object _state)
{
    ClientState _previousClientState = this._clientState;
    this._clientState = ClientState.ucClientStateSignedIn;
    // The IMClientStateChangedEventData class implements the 
    // IClientStateChangedEventData interface.
    IMClientStateChangedEventData eventData = 
        new IMClientStateChangedEventData(_previousClientState, 
        this._clientState);
    if (_userUri != null)
    {
        // During the sign-in process, create a new contact with
        // the contact information of the currently signed-in user.
        this._self = new IMClientSelf(IMContact.BuildContact(_userUri));
    }
    // Raise the _ILyncClientEvents.OnStateChanged event.
    OnStateChanged(this, eventData as UC.ClientStateChangedEventData);
    
    return this._asyncOperation;
    }
}

```

下面的代码示例演示如何设置使用 _ **ILyncClientEvents**和 _ **IUCOfficeIntegrationEvents**接口的事件侦听器。 
  
```cs
using Microsoft.Office.Uc;
using System;
using System.Runtime.CompilerServices;
using System.Runtime.InteropServices;
namespace SampleImplementation
{
    // Note: UCOfficeIntegration inherits from both IUCOfficeIntegration and _IUCOfficeIntegrationEvents_Event
    [ClassInterface(ClassInterfaceType.None), Guid("13c41ef9-eb90-4e94-8a7c-1e9d686bc019"), ComVisible(true)]
    [ComSourceInterfaces(typeof(_IUCOfficeIntegrationEvents))]
    public class MyInstantMessengerOfficeIntegration : UCOfficeIntegration
    {
        #region IUCOfficeIntegration implementation
        public string GetAuthenticationInfo(string _version)
        {
            return "";
        }
        public object GetInterface(string _version, OIInterface _interface)
        {
            return null;
        }
        public OIFeature GetSupportedFeatures(string _version)
        {
            return OIFeature.oiFeatureAddOneNoteToConversation;
        }
        #endregion
        #region _IUCOfficeIntegrationEvents support
        // This event implements void _IUCOfficeIntegrationEvents.OnShuttingDown();
        public event _IUCOfficeIntegrationEvents_OnShuttingDownEventHandler OnShuttingDown;
        // This method is called by the IM application when it is beginning to shut down.
        // The method will raise the OnShuttingDown event which is translated by .NET COM interop layer
        // into a call to _IUCOfficeIntegrationEvents.OnShuttingDown.
        // This notifies Office applications that the IM application is going away.
        internal void RaiseOnShuttingDownEvent()
        {
            if (this.OnShuttingDown != null)
            {
                this.OnShuttingDown();
            }
        }
        #endregion
    }
    // Note: LyncClient inherits from both ILyncClient and _ILyncClientEvents_Event
    // You must implement LyncClient because the event handlers in _ILyncClientEvents expect you to pass a LyncClient interface.
    [ComVisible(true)]
    [ComSourceInterfaces(typeof(_ILyncClientEvents))]
    public class MyInstantMessengerOfficeIntegration2 :
        Client,
        Client2,
        LyncClient
    {
        #region Interfaces
        public LyncClientCapabilityTypes Capabilities
        {
            get
            {
                throw new NotImplementedException();
            }
        }
        public ConferenceScheduler ConferenceScheduler
        {
            get
            {
                throw new NotImplementedException();
            }
        }
        public ContactManager ContactManager
        {
            get
            {
                throw new NotImplementedException();
            }
        }
        public ConversationManager ConversationManager
        {
            get
            {
                throw new NotImplementedException();
            }
        }
        public DelegatorClient[] DelegatorClients
        {
            get
            {
                throw new NotImplementedException();
            }
        }
        public DeviceManager DeviceManager
        {
            get
            {
                throw new NotImplementedException();
            }
        }
        public bool InSuppressedMode
        {
            get
            {
                throw new NotImplementedException();
            }
        }
        public ContactManager PrivateContactManager
        {
            get
            {
                throw new NotImplementedException();
            }
        }
        public RoomManager RoomManager
        {
            get
            {
                throw new NotImplementedException();
            }
        }
        public Self Self
        {
            get
            {
                throw new NotImplementedException();
            }
        }
        public ClientSettings Settings
        {
            get
            {
                throw new NotImplementedException();
            }
        }
        public SignInConfiguration SignInConfiguration
        {
            get
            {
                throw new NotImplementedException();
            }
        }
        public ClientState State
        {
            get
            {
                throw new NotImplementedException();
            }
        }
        public ClientType Type
        {
            get
            {
                throw new NotImplementedException();
            }
        }
        public string Uri
        {
            get
            {
                throw new NotImplementedException();
            }
        }
        public Utilities Utilities
        {
            get
            {
                throw new NotImplementedException();
            }
        }
        public ApplicationRegistration CreateApplicationRegistration(string _appGuid, string _appName)
        {
            throw new NotImplementedException();
        }
        public AsynchronousOperation Initialize(string _clientName, string _version = "0", string _clientShortName = "0", string _clientNameAbbreviation = "0", string _clientLongName = "0", SupportedFeatures _supportedFeatures = SupportedFeatures.ucAllFeatures, [IUnknownConstant] object _CommunicatorClientCallback = null, object _state = null)
        {
            throw new NotImplementedException();
        }
        public AsynchronousOperation Shutdown([IUnknownConstant] object _CommunicatorClientCallback, object _state)
        {
            throw new NotImplementedException();
        }
        public AsynchronousOperation SignIn(string _userUri = "0", string _domainAndUsername = "0", string _password = "0", [IUnknownConstant] object _CommunicatorClientCallback = null, object _state = null)
        {
            throw new NotImplementedException();
        }
        public AsynchronousOperation SignOut([IUnknownConstant] object _CommunicatorClientCallback, object _state)
        {
            throw new NotImplementedException();
        }
        #endregion
        #region _ILyncClientEvents support
        public event _ILyncClientEvents_OnStateChangedEventHandler OnStateChanged;
        public event _ILyncClientEvents_OnNotificationReceivedEventHandler OnNotificationReceived;
        public event _ILyncClientEvents_OnCredentialRequestedEventHandler OnCredentialRequested;
        public event _ILyncClientEvents_OnSignInDelayedEventHandler OnSignInDelayed;
        public event _ILyncClientEvents_OnCapabilitiesChangedEventHandler OnCapabilitiesChanged;
        public event _ILyncClientEvents_OnDelegatorClientAddedEventHandler OnDelegatorClientAdded;
        public event _ILyncClientEvents_OnDelegatorClientRemovedEventHandler OnDelegatorClientRemoved;
        // Notifies Office apps that the IM client state (signed out, signing in, singed in, signing out, etc) has changed.
        internal void RaiseOnStateChangedEvent(ClientStateChangedEventData eventData)
        {
            if (this.OnStateChanged != null)
            {
                this.OnStateChanged(this, eventData);
            }
        }
        // Notifies Office apps that the IM client has received a notification event from MAPI (e.g. autodiscover has finished)
        internal void RaiseOnNotificationReceivedEvent(LyncClientNotificationReceivedEventData eventData)
        {
            if (this.OnNotificationReceived != null)
            {
                this.OnNotificationReceived(this, eventData);
            }
        }
        // Notifies Office apps that the IM client has received a request for credentials for some operation (e.g. sign in, web search)
        internal void RaiseOnCredentialRequestedEvent(CredentialRequestedEventData eventData)
        {
            if (this.OnCredentialRequested != null)
            {
                this.OnCredentialRequested(this, eventData);
            }
        }
        // Notifies Office apps that the IM client has been delayed from signing in and gives an estimated delay time.
        internal void RaiseOnSignInDelayedEvent(SignInDelayedEventData eventData)
        {
            if (this.OnSignInDelayed != null)
            {
                this.OnSignInDelayed(this, eventData);
            }
        }
        // Notifies Office apps that the capabilities of this IM client have changed.
        internal void RaiseOnCapabilitiesChangedEvent(PreferredCapabilitiesChangedEventData eventData)
        {
            if (this.OnCapabilitiesChanged != null)
            {
                this.OnCapabilitiesChanged(this, eventData);
            }
        }
        // Notifies Office apps that a DelegatorClient object has been added to the IM client object.
        internal void RaiseOnDelegatorClientAdded(DelegatorClientCollectionEventData eventData)
        {
            if (this.OnDelegatorClientAdded != null)
            {
                this.OnDelegatorClientAdded(this, eventData);
            }
        }
        // Notifies Office apps that a DelegatorClient object has been removed from the IM client object.
        internal void RaiseOnDelegatorClientRemoved(DelegatorClientCollectionEventData eventData)
        {
            if (this.OnDelegatorClientRemoved != null)
            {
                this.OnDelegatorClientRemoved(this, eventData);
            }
        }
        #endregion
    }
}
```

### <a name="iautomation-interface"></a>IAutomation 接口
<a name="off15_IMIntegration_ImplementRequired_IAutomation"> </a>

**IAutomation**界面自动化了 IM 客户端应用程序的功能。 它可以用于开始对话，加入会议，并提供扩展性窗口上下文。 
  
表 4 显示必须的继承**IAutomation**类中实现的成员。
  
> [!NOTE]
> 表中未列出的**IAutomation**任何的接口成员必须存在但不需要实现。 已存在，但未实现的成员可以引发**NotImplementedException**或**E_NOTIMPL**错误。 
> 
> 有关**IAutomation**接口和其成员的详细信息，请参阅[UCCollaborationLib.IAutomation](http://msdn.microsoft.com/library/UCCollaborationLib.IAutomation)。 
  
**表 4。IAutomation 接口实现**

|**成员**|**说明**|
|:-----|:-----|
|**StartConversation**方法  <br/> |开始使用指定的会话形式的对话。 返回**IConversationWindow**的实例。  <br/> |
   
## <a name="implementing-contact-presence-integration"></a>实现联系人的状态集成
<a name="off15_IMIntegration_ImplementIMFeatures"> </a>

除了前面所述的三个所需接口，可以使用几个重要启用 Office 中的联系人的状态功能的其他接口。 其中包括：
  
- [IContact](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContact)或**IContact2**接口。 
    
- [ISelf](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ISelf)界面中。 
    
- [IContactManager](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactManager)和[_IContactManagerEvents](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactManager)接口。 
    
- [IGroup](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IGroup)和[IGroupCollection](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IGroup)接口。 
    
- [IContactSubscription](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactSubscription)界面中。 
    
- [IContactEndPoint](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactEndPoint)界面中。 
    
- [ILocaleString](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ILocaleString)接口 
    
### <a name="icontact-interface"></a>IContact 接口
<a name="off15_IMIntegration_ImplementRequired_IContact"> </a>

**IContact**界面代表 IM 客户端应用程序用户。 接口公开状态、 可用的形式、 组成员身份和用户的联系人类型属性。 与另一个用户开始对话，您必须提供**IContact**该用户实例。
  
表 5 显示了必须的继承**IContact**类中实现的成员。
  
> [!NOTE]
> 表中未列出的**IContact**任何的接口成员必须存在但不需要实现。 已存在，但未实现的成员可以引发**NotImplementedException**或**E_NOTIMPL**错误。 
>
> 有关**IContact**接口和其成员的详细信息，请参阅[UCCollaborationLib.IContact](http://msdn.microsoft.com/library/UCCollaborationLib.IContact)。 
  
**表 5。IContact 接口实现**

|**成员**|**说明**|
|:-----|:-----|
|**CanStart**方法  <br/> |如果可以在该联系人上启动给定的类型的形式，则返回**true** 。  <br/> |
|**GetContactInformation**方法  <br/> |从发布联系人获取一个状态项。  <br/> |
|**BatchGetContactInformation**方法  <br/> |从发布联系人获取多个状态项目。  <br/> |
|**Settings**属性  <br/> |获取联系人属性的集合。  <br/> |
|**CustomGroups**属性  <br/> |获取组的成员的联系人的集合。  <br/> |
   
在初始化过程中，Office 应用程序调用**IContact.CanStart**方法来确定本地用户的 IM 功能。 **CanStart**方法所需的 __modalityTypes_形参的实参作为[UCCollaborationLib.ModalityTypes](http://msdn.microsoft.com/library/UCCollaborationLib.ModalityTypes)枚举中的标志。 如果当前用户可以参与请求形式 （即，用户是支持即时消息、 音频和视频消息，或应用程序共享的）， **CanStart**方法返回**true**。
  
```cs
public bool CanStart(ModalityTypes _modalityTypes)
{
    // Define the capabilities of the current IM client application
    // user by using flags from the ModalityTypes enumeration.
    ModalityTypes userCapabilities = 
        ModalityTypes.ucModalityInstantMessage | 
        ModalityTypes.ucModalityAudioVideo | 
        ModalityTypes.ucModalityAppSharing;
    // Perform a simple test for equivalency.
    if (_modalityType == userCapabilities) 
    {
        return true;
    }
    else 
    {
        return false;
    }
}

```

**GetContactInformation**方法从**IContact**对象检索有关该联系人的信息。 调用的代码需要在值传递 __contactInformationType_参数，指示要检索的数据的[UCCollaborationLib.ContactInformationType](http://msdn.microsoft.com/library/UCCollaborationLib.ContactInformationType)枚举中。 
  
```cs
public object GetContactInformation(
    ContactInformationType _contactInformationType)
{
    // Determine the information to return from the contact's data based
    // on the value passed in for the _contactInformationType parameter.
    switch (_contactInformationType)
    {
        case ContactInformationType.ucPresenceEmailAddresses:
        {
            // Return the URI associated with the contact.
            string returnValue = this.Uri.ToLower().Replace("sip:", String.Empty);
            return returnValue;
        }
        case ContactInformationType.ucPresenceDisplayName:
        {
            // Return the display name associated with the contact.
            string returnValue = this._DisplayName;
            return returnValue;
        }
        default:
        {
            throw new NotImplementedException;
        }
        // Additional implementation details omitted.
    }
}
```

类似于**GetContactInformation**， **BatchGetContactInformation**方法检索有关该联系人的多个状态项目从**IContact**对象。 调用的代码需要从**ContactInformationType**枚举 __contactInformationTypes_参数传递的值的数组中。 该方法返回[UCCollaborationLib.IContactInformationDictionary](http://msdn.microsoft.com/library/UCCollaborationLib.IContactInformationDictionary)对象，其中包含请求的数据。 
  
```cs
public IMClientContactInformationDictionary BatchGetContactInformation(
    ContactInformationType[] _contactInformationTypes)
{
    // The IMClientContactInformationDictionary class implements the
    // IContactInformationDictionary interface.
    IMClientContactInformationDictionary contactDictionary = 
        new IMClientContactInformationDictionary();
    foreach (ContactInformationType type in _contactInformationTypes)
    {
        // Call GetContactInformation for each type of contact 
        // information to retrieve. This code adds a new entry to
        // a Dictionary object exposed by the
        // ContactInformationDictionary property.
        contactDictionary.ContactInformationDictionary.Add(
            type, this.GetContactInformation(type));
    }
    return contactDictionary;
}
```

**IContact.Settings**属性返回**IContactSettingDictionary**对象，该对象包含有关该联系人的自定义属性。 
  
```cs
public IMClientContactSettingDictionary Settings
{
    get
    {
       // The IMClientContactSettingDictionary class implements
       // the IContactSettingDictionary interface.
       return new IMClientContactSettingDictionary();
    }
}
```

**IContact.CustomGroups**属性返回**IGroupCollection**对象，该对象包含所有联系人是其成员的组。 
  
```cs
public IMClientGroupCollection CustomGroups
{
    get {
       // The IMClientGroupCollection class implements
       // the IGroupCollection interface.
        return new IMClientGroupCollection();
    }
}
```

### <a name="iself-interface"></a>ISelf 接口
<a name="off15_IMIntegration_ImplementRequired_ISelf"> </a>

在初始化过程中，Office 应用程序获取的数据为当前用户通过访问必须返回**ISelf**对象的**ILyncClient.Self**属性。 **ISelf**界面代表本地、 已登录的 IM 客户端应用程序用户。 
  
表 6 显示必须的继承**ISelf**类中实现的成员。
  
> [!NOTE]
> 表中未列出的**ISelf**任何的接口成员必须存在但不需要实现。 已存在，但未实现的成员可以引发**NotImplementedException**或**E_NOTIMPL**错误。 
  
**表 6。ISelf 接口实现**

|**成员**|**说明**|
|:-----|:-----|
|**联系人**属性  <br/> |获取与本地用户关联的**IContact**对象。  <br/> |
   
通过的**ISelf.Contact**属性 （返回**IContact**对象） 公开状态、 可用的形式、 组成员和本地用户的联系人类型属性。 在初始化过程中，Office 应用程序访问**ISelf.Contact**属性来获取对本地用户的联系人信息的引用。 
  
使用以下代码定义从**ISelf**接口实现**联系人**属性继承的类。 
  
```cs
[ComVisible(true)]
public class IMClientSelf : ISelf
{
    // Declare a private field to store contact data for local user.
    private IMClientContact _contactData;
    // In the constructor for the ISelf object, the calling code 
    // must supply contact data.
    public IMClientSelf (IMClientContact _selfContactData)
    {
        this._contactData = _selfContactData;
    }
    // When accessed, the Contact property returns a reference
    // to the IContact object that represents the local user.
    public IMClientContact Contact
    {
        get
        {
            return this._contactData as IMClientContact;
        }
    }
    // Additional implementation details omitted.
}
```

### <a name="icontactmanager-and-icontactmanagerevents-interfaces"></a>IContactManager 和 _IContactManagerEvents 接口
<a name="off15_IMIntegration_ImplementRequired_IContactManager"> </a>

**IContactManager**对象管理本地用户，包括本地用户自己的联系人信息的联系人。 Office 应用程序使用**IContactManager**对象访问**IContact**对象对应于本地用户的联系人。 
  
表 7 显示了必须继承自**IContactManager**和 **_IContactManagerEvents**类中实现的成员。
  
> [!NOTE]
> 表中未列出的**IContactManager**任何的接口成员必须存在但不需要实现。 已存在，但未实现的成员可以引发**NotImplementedException**或**E\_NOTIMPL**错误。 
>
> 有关**IContactManager** **_IContactManagerEvents**接口和其成员的详细信息，请参阅[UCCollaborationLib.IContactManager](http://msdn.microsoft.com/library/UCCollaborationLib.IContactManager)和[UCCollaborationLib._IContactManagerEvents](http://msdn.microsoft.com/library/UCCollaborationLib._IContactManagerEvents)。 
  
**表 7。IContactManager 和 _IContactManagerEvents 接口实现**

|**接口**|**成员**|**说明**|
|:-----|:-----|:-----|
|**IContactManager** <br/> |**GetContactByUri**方法  <br/> |查找或使用联系人 URI 创建新的联系人实例。  <br/> |
||**CreateSubscription**方法  <br/> |创建一个可用于批处理订阅或查询的**ISubscription**对象。  <br/> |
||**Lookup**方法  <br/> |查找联系人或通讯组。  <br/> |
|**_IContactManagerEvents** <br/> |**OnGroupAdded**事件  <br/> |一组添加到组集合时引发。 可以从**IContactManager.Groups**属性获取更新的组集合。  <br/> |
||**OnGroupRemoved**事件  <br/> |从一组中删除组时引发。 可以从**IContactManager.Groups**属性获取更新的组集合。  <br/> |
||**OnSearchProviderStateChanged**事件  <br/> |搜索提供程序的状态发生变化时引发。  <br/> |
   
Office 调用**IContactManager.GetContactByUri**获取联系人的状态信息，使用该联系人的 SIP 地址。 当联系人配置为在 Active Directory 中的 SIP 地址时，Office 将确定此地址的联系人和呼叫**GetContactByUri**，传递此 __contactUri_参数中的联系人的 SIP 地址。 
  
当 Office 无法确定联系人的 SIP 地址时，它会调用**IContactManager.Lookup**方法使用 IM 服务查找 SIP。 此处 Office 传入它能找到该联系人 （例如，只需为该联系人的电子邮件地址） 的最佳数据。 **Lookup**方法异步返回**AsynchronousOperation**对象。 当调用回调时，该**查阅**方法应返回联系人除了 URI 的操作成功与否。 
  
```cs
public IMClientContact GetContactByUri(string _contactUri)
{
    // Declare a Contact variable to contain information about the contact.
    IMClientContact tempContact = null;
    // The _groupCollections field is an IGroupCollection object. Iterate 
    // over each group in collection to see if the 
    // contact is a part of the group.
    foreach (IMClientGroup group in this._groupCollections)
    {
       if (group.TryGetContact(_contactUri, out tempContact))
       {
           break;
       }
    }
    // Check to see that the URI returned a valid contact. If it
    // did not, create a new contact.
    if (tempContact == null)
    {
        tempContact = IMClientContact.BuildContact(_contactUri);
    }
    // Return the contact to the calling code.
    return tempContact;
}
```

Office 应用程序需要订阅的单个联系人的状态更改。 因此，联系人的状态更改时，IM 服务器通知 IM 客户端应用程序，从而警报的 Office 应用程序。 若要执行此操作，Office 应用程序，请调用**IContactManager.CreateSubscription**方法可创建的此请求的新**IContactSubscription**对象。 
  
```cs
// Declare a private field to contain an IContactSubscription object.
private IMClientContactSubscription _contactSubscription;
// Return the IContactSubscription object associated 
// with the IContactManager object.
public IMClientContactSubscription CreateSubscription()
{
    return this._contactSubscription;
}
```

### <a name="igroup-and-igroupcollection-interfaces"></a>IGroup 和 IGroupCollection 接口
<a name="off15_IMIntegration_ImplementRequired_IGroup"> </a>

**IGroup**对象代表与其他属性确定联系人集合通过集体组名的联系人的集合。 **IGroupCollection**对象代表由本地用户和 IM 客户端应用程序定义的**IGroup**对象的集合。 Office 应用程序使用的**IGroupCollection**和**IGroup**对象来访问本地用户的联系人。 
  
表 9 显示了必须在下表中从**IGroup**和**IGroupCollection**继承的类中实现的成员。 
  
> [!NOTE]
> 表中未列出的**IGroup**任何的接口成员必须存在但不需要实现。 已存在，但未实现的成员可以引发**NotImplementedException**或**E_NOTIMPL**错误。 
>
> 有关的**IGroup**和**IGroupCollection**接口及其成员的详细信息，请参阅[UCCollaborationLib.IGroup](http://msdn.microsoft.com/library/UCCollaborationLib.IGroup)和[UCCollaborationLib.IGroupCollection](http://msdn.microsoft.com/library/UCCollaborationLib.IGroupCollection)。 
  
**表 9。IGroup 和 IGroupCollection 接口实现**

|**接口**|**成员**|**说明**|
|:-----|:-----|:-----|
|**IGroupCollection** <br/> |**Count** 属性  <br/> |返回集合中的**IGroup**对象的计数  <br/> |
||**Item** 属性  <br/> |返回集合中指定索引处的**IGroup**对象。  <br/> |
|**IGroup** <br/> |**Id**属性  <br/> |返回组中的 ID。  <br/> |
   
时 Office 应用程序获取本地用户的信息，它通过调用返回**IGroupCollection**对象的**IContact.CustomGroups**属性来访问联系人 （本地用户） 的组成员资格。 **IGroupCollection**必须包含**IGroup**对象的数组 （或**列表**）。 从**IGroupCollection**派生的类必须公开**Count**属性，该集合和索引器方法， **this(int)**，从集合中返回一个**IGroup**对象中返回的项目数。 
  
### <a name="icontactsubscription-interface"></a>IContactSubscription 接口
<a name="off15_IMIntegration_ImplementRequired_IContactSubscription"> </a>

**IContactSubscription**界面允许您指定要接收有关更新的状态信息和触发通知的类型的状态信息的联系人。 Office 应用程序使用**IContactSubscription**对象注册更改联系人的状态。 
  
表 10 显示必须继承**IContactSubscription**类中实现的成员。
  
> [!NOTE]
> 表中未列出的**IContactSubscription**任何的接口成员必须存在但不需要实现。 已存在，但未实现的成员可以引发**NotImplementedException**或**E_NOTIMPL**错误。
>
> 有关**IContactSubscription**接口和其成员的详细信息，请参阅[UCCollaborationLib.IContactSubscription](http://msdn.microsoft.com/library/UCCollaborationLib.IContactSubscription)。 
  
**表 10。IContactSubscription 接口实现**

|**成员**|**说明**|
|:-----|:-----|
|**AddContact**方法  <br/> |将联系人添加到订阅对象。  <br/> |
|**Subscribe**方法  <br/> |帮助 IM 客户端应用程序监视联系人的状态。  <br/> |
   
**IContactSubscription**接口必须包含对监视，使用数组或**列表**的所有**IContact**对象的引用。 **IContactSubscription.AddContact**方法添加**IContact**对象**IContactSubscription**对象的基础数据结构，从而添加新联系人的状态更改监视。 
  
```cs
// Store references to all of the IContact objects to subscribe to.
private List<IMClientContact> _subscribedContacts;
// Add a new IContact object to the collection of contacts.
public void AddContact(IMClientContact _contact)
{
    this._subscribedContacts.Add(_contact);
}
```

**IContactSubscription.Subscribe**方法允许访问联系人的状态观察者 IM 客户端应用程序。 它可以使用的轮询策略获取订阅 IM 客户端应用程序中的服务器的联系人的状态。 在其中为外部用户的联系人列表 （例如，从较大的公用网络） 的某个人的请求状态的情况下有用的**Subscribe**方法。 
  
### <a name="icontactendpoint-interface"></a>IContactEndPoint 接口
<a name="off15_IMIntegration_ImplementRequired_IContactEndPoint"> </a>

**IContactEndPoint**表示电话号码的电话号码的联系人的集合中。 
  
表 11 显示了必须在从**IContactEndPoint**继承的类中实现的成员。
  
> [!NOTE]
> 表中未列出的**IContactEndPoint**任何的接口成员必须存在但不需要实现。 已存在，但未实现的成员可以引发**NotImplementedException**或**E_NOTIMPL**错误。
>
> 有关**IContactEndPoint**接口和其成员的详细信息，请参阅[UCCollaborationLib.IContactEndpoint](http://msdn.microsoft.com/library/UCCollaborationLib.IContactEndpoint)。 
  
**表 11。IContactEndPoint 接口实现**

|**成员**|**说明**|
|:-----|:-----|
|**DisplayName**属性  <br/> |获取显示字符串。  <br/> |
|**Type** 属性  <br/> |获取联系人的终结点类型  <br/> |
|**Uri** 属性  <br/> |获取联系人的 URI。  <br/> |
   
### <a name="ilocalestring-interface"></a>ILocaleString 接口
<a name="off15_IMIntegration_ImplementRequired_ILocaleString"> </a>

**ILocaleString**是包含的本地化的字符串和本地化的区域设置 ID 的本地化的字符串结构。 **ILocaleString**接口用于设置联系人卡片上的自定义状态字符串的格式。 
  
表 12 显示必须继承**ILocaleString**类中实现的成员。
  
> [!NOTE]
> 表中未列出的**ILocaleString**任何的接口成员必须存在但不需要实现。 已存在，但未实现的成员可以引发**NotImplementedException**或**E_NOTIMPL**错误。
>
> 有关**ILocalString**接口和其成员的详细信息，请参阅[UCCollaborationLib.ILocaleString](http://msdn.microsoft.com/library/UCCollaborationLib.ILocaleString)。 
  
**表 12。ILocaleString 接口实现**

|**成员**|**说明**|
|:-----|:-----|
|**LocaleId**属性  <br/> |获取区域设置 id。  <br/> |
|**Value**属性  <br/> |获取的字符串。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [UCCollaborationLib](http://msdn.microsoft.com/library/UCCollaborationLib)命名空间 
    

