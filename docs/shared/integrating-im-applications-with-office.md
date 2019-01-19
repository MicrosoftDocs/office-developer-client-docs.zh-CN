---
title: 将 IM 应用程序与 Office 集成
manager: soliver
ms.date: 07/25/2016
ms.audience: Developer
ms.assetid: beba316b-1dfe-4e1b-adae-42418906c177
description: 本文介绍如何配置即时消息 (IM) 客户端应用程序，以便它与 Office 2013 中的社交功能集成，包括显示状态并从联系人卡片发送即时消息。
localization_priority: Priority
ms.openlocfilehash: b3add86f011e016b1b6ea1a74f425f3f1deab002
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28700708"
---
# <a name="integrating-im-applications-with-office"></a>将 IM 应用程序与 Office 集成

本文介绍如何配置即时消息 (IM) 客户端应用程序，以便它与 Office 2013 中的社交功能集成，包括显示状态并从联系人卡片发送即时消息。
  
如果你对本技术文章或其描述的流程有任何疑问或意见，则可以通过发送电子邮件至 [docthis@microsoft.com](mailto:docthis@microsoft.com) 来直接与 Microsoft 联系。
  
## <a name="introduction"></a>简介
<a name="off15_IMIntegration_Intro"> </a>

Office 2013 提供与 IM 客户端应用程序（包括 Lync 2013）的丰富集成功能。 此集成在 Word 2013、Excel 2013、PowerPoint 2013、Outlook 2013、Visio 2013、Project 2013 和 OneNote 2013 中为用户提供了 IM 功能，并且在 SharePoint 2013 页面上提供了状态集成。 用户可以查看其联系人列表中的联系人照片、姓名、当前状态和数据。 他们可以直接从联系人卡片（Office 2013 中显示联系信息和通信选项的 UI 元素）开始 IM 会话、视频呼叫或电话呼叫。 Office 2013 可让你轻松与联系人保持联系，而无需离开你的电子邮件或文档。 
  
> [!NOTE]
> 本文使用术语 IM 客户端应用程序专门指代安装在与 IM 服务通信的用户计算机上的应用程序。 例如，可将 Lync 2013 视为 IM 客户端应用程序。 本文未提供有关 IM 客户端应用程序如何与 IM 服务进行通信或 IM 服务本身的详细信息。 
  
你可以自定义 IM 客户端应用程序，以便它与 Office 通信。 具体来说，你可以修改 IM 应用程序，以便在 Office UI 中显示以下信息：
  
- 联系人照片。
    
- 联系人姓名。
    
- 联系人个人状态说明。
    
- 联系人当前状态。
    
- 联系人状态字符串（例如“有空”或“外出”）。
    
- 联系人具有的功能字符串（例如“视频就绪”）。
    
- 一键式 IM 启动。
    
- 一键式视频呼叫启动。
    
- 一键式电话呼叫启动（包括 SIP、电话号码、语音邮件和呼叫新号码）。
    
- 联系人管理（添加到 IM 组）。
    
- 联系人位置和时区。
    
- 联系人数据、电话号码、电子邮件地址、职务和公司名称。
    
**图 1. Office 2013 中的联系人卡片**

![Office 2013 中的联系人卡片](media/ocom15_peoplecard.png "Office 2013 中的联系人卡片")
  
为了实现与 Office 的集成，IM 客户端应用程序必须实现由 Office 提供的一组接口才能连接到它。 用于此集成的 API 包含在 Microsoft.Office.UC.dll 文件内的 [ UCCollborationLib ](https://msdn.microsoft.com/en-au/library/uccollaborationlib.aspx) 命名空间中，该文件与包含 Lync/Skype for Business 的 Office 2013 版本安装在一起。 ** UCCollaborationLib ** 命名空间包含为与 Office 集成而必须实现的接口。 
  
> [!IMPORTANT] 
> 所需接口的类型库嵌入在 Lync 2013/Skype for Business 中。 对于第三方集成商，仅当目标计算机上安装了 Lync 2013 和 Skype for Business 时，此方法才有效。 如果要使用 Office Standard 进行集成，则需要提取类型库并将其安装在目标计算机上。 [Lync 2013 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=36824) 包含 Microsoft.Office.UC.dll 文件。 
  
> [!NOTE]
>  少数 Office 2010 应用程序可以与第三方 IM 提供商的应用程序进行类似的集成：Outlook 2010、Word 2010、Excel 2010、PowerPoint 2010 和 SharePoint Server 2010（使用 ActiveX 控件）。 与 Office 2013 集成所需的许多步骤也适用于 Office 2010。 Office 2010 与 IM 提供商的应用程序集成的方式有几个主要差异： 
>  - Office 2010 不显示联系人的照片。 
>  - 你必须单独从 Office 2010 下载 Microsoft.Office.Uc.dll 文件。 [Lync 2010 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=18898) 包含适用于 Office 2010 的 Microsoft.Office.UC.dll 文件。 
>  - 当 Office 应用程序在 IM 客户端应用程序上调用 [ IUCOfficeIntegration.GetAuthenticationInfo ](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IUCOfficeIntegration) 方法时，它会传入字符串“14.0.0.0”。 
>  - Office 2010 一旦连接到 IM 客户端应用程序，就会枚举所有组和联系人。 
  
## <a name="how-office-integrates-with-an-im-client-application"></a>Office 如何与 IM 客户端应用程序集成
<a name="off15_IMIntegration_How"> </a>

当 Office 2013 应用程序启动时，它将完成以下流程以与默认 IM 客户端应用程序集成：
  
1. 检查注册表以发现默认的 IM 客户端应用程序，然后连接到它。
    
2. 使用 IM 客户端应用程序进行身份验证。
    
3. 连接到 IM 客户端应用程序公开的特定接口。
    
4. 确定当前登录用户（本地用户）具有的功能，包括获取用户的联系人、确定用户的状态以及用户具有的 IM 功能（即时消息、视频聊天、VOIP 等）。
    
5. 获取本地用户联系人的状态信息。
    
6. 当 IM 客户端应用程序关闭时，Office 2013 应用程序将自动断开连接。
    
### <a name="discovering-the-im-application"></a>发现 IM 应用程序

Office 应用程序会在注册表中查找几个特定的注册表项和条目，以便发现默认的 IM 客户端应用程序。 如果发现默认的 IM 客户端应用程序，它会尝试连接到它。
  
Office 应用程序发现默认 IM 客户端应用程序的过程如下：
  
1. Office 应用程序会查看是否在注册表中设置了 HKEY_CURRENT_USER\Software\IM Providers\DefaultIMApp 子项，并读取其中列出的应用程序名称。
    
2. 然后，Office 应用程序将读取 HKEY_CURRENT_USER\Software\IM Providers\ _Application name_\UpAndRunning 注册表项，并监视值更改。
    
3. Office 应用程序接下来会读取 HKEY_LOCAL_MACHINE\Software\IM Providers\ _Application name_ 注册表项，并获取存储在其中的 ProcessName 和 class ID (CLSID) 值。 
    
4. 一旦 IM 客户端应用程序成功完成其启动序列并为状态集成正确注册所有类，它会将 HKEY_CURRENT_USER\Software\IM Providers\ _Application name_\UpAndRunning 注册表项设置为“2”，表示客户端应用程序正在运行。
    
5. 当 Office 应用程序发现 HKEY_CURRENT_USER\Software\IM Providers\ _Application name_\UpAndRunning 注册表项已设置为“2”时，它会检查计算机上正在运行的进程列表以查找 IM 客户端应用程序的进程名称。
    
6. 在找到 IM 客户端应用程序使用的进程后，Office 应用程序将使用 CLSID 来调用 **CoCreateInstance**，以便与作为进程外 COM 服务器的 IM 客户端应用程序建立连接。 
    
### <a name="authenticating-the-connection-to-the-im-application"></a>验证与 IM 应用程序的连接

当 Office 应用程序与 IM 客户端应用程序建立连接后，它将执行以下操作：
  
1. Office 应用程序将调用 [IUnknown::QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx) 方法来检查 [IUCOfficeIntegration](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IUCOfficeIntegration) 接口。 
    
2. 然后，Office 应用程序将调用 **IUCOfficeIntegration.GetAuthenticationInfo** 方法，以便传入支持的最高集成版本（例如，“15.0.0.0”）。 
    
3. 如果 IM 客户端应用程序支持作为参数传入的 Office 版本，则该应用程序会将以下硬编码的 XML 字符串返回给调用代码：
    
    `<authenticationinfo>`
    
   > [!NOTE]
   > 由于遗留原因，如果 IM 客户端应用程序支持作为参数传入的 Office 版本，则必须将准确值 `<authenticationinfo>` 返回到对 ** GetAuthenticationInfo** 的调用。 
  
4. 如果 IM 客户端应用程序无法返回值，则 Office 应用程序将重新使用下一个受支持的 Office 版本（例如，“14.0.0.0”）来调用 **GetAuthenticationInfo** 方法。 
    
5. 一旦 Office 确定 IM 客户端应用程序支持 IM 和状态集成，它就会连接到一组所需的接口以完成初始化。 （有关详细信息，请参阅[连接到所需的接口](#off15_IMIntegration_HowConnect)。）
    
如果 Office 应用程序在上述任何步骤中遇到错误，它将退出，并且在 Office 应用程序的会话期间不会再次建立状态集成。 
  
### <a name="connecting-to-required-interfaces"></a>连接到所需的接口
<a name="off15_IMIntegration_HowConnect"> </a>

在验证与 IM 客户端应用程序的连接后，Office 应用程序会尝试连接到 IM 客户端应用程序公开的一组必需接口。 为此，Office 应用程序将执行以下操作：
  
- Office 应用程序将通过调用 **IUCOfficeIntegration.GetInterface** 方法来获取 [ILyncClient](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ILyncClient) 对象，以便从 [UCCollaborationLib.OIInterface](https://msdn.microsoft.com/library/UCCollaborationLib.OIInterface) 枚举传入 **oiInterfaceLyncClient** 常量。 
    
- Office 应用程序将通过调用 **IUCOfficeIntegration.GetInterface** 方法来获取 [IAutomation](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IAutomation) 对象，以便从 **OIInterface** 枚举传入 **oiInterfaceAutomation** 常量。 
    
- Office 应用程序将设置 [_ILyncClientEvents](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ILyncClient) 事件侦听器。 
    
- Office 应用程序将设置 [_IUCOfficeIntegrationEvents](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IUCOfficeIntegration) 事件侦听器。 
    
- Office 应用程序将通过访问 **ILyncClient.State** 属性从 IM 客户端应用程序获取登录状态。 
    
- Office 应用程序将通过调用 **IUCOfficeIntegration.GetSupportedFeatures** 方法来获取 IM 客户端应用程序的功能，它将从 [UCCollaborationLib.OIFeature](https://msdn.microsoft.com/library/UCCollaborationLib.OIFeature) 枚举返回一个标记。 
    
- Office 应用程序将访问 **ILyncClient.Self** 属性以获取对 [ISelf](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ISelf) 对象的引用。 
    
### <a name="retrieving-the-capabilities-of-the-local-user"></a>检索本地用户具有的功能
<a name="off15_IMIntegration_HowConnect"> </a>

Office 应用程序将通过执行以下操作来获取本地用户具有的功能：
  
1. 如果 IM 客户端应用程序支持 **IClient2** 接口，则 Office 会尝试通过访问 **IClient2.PrivateContactManager** 属性来获取 [IContactManager](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactManager) 对象。 
    
2. 如果 IM 客户端应用程序不支持 **IClient2** 接口，则 Office 应用程序会尝试通过访问 **ILyncClient.ContactManager** 属性来获取 **IContactManager** 对象。 在建立任何其他 IM 功能之前，IM 客户端应用程序必须成功返回 **IContactManager** 对象。 
    
3. Office 应用程序将访问 **ILyncClient.Uri** 属性，然后调用 **IContactManager.GetContactByUri** 以获取与本地用户关联的 [IContact](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContact) 对象。 
    
4. 然后，Office 应用程序将对 **IContact.CanStart** 进行多次调用以建立本地用户具有的功能，并依次传入 **ModalityTypes.ucModalityInstantMessage** 和 **ModalityTypes.ucModalityAudioVideo** 的值。 
    
### <a name="retrieving-contact-presence"></a>检索联系人状态
<a name="off15_IMIntegration_HowConnect"> </a>

Office 应用程序将通过执行以下操作获取联系人状态（包括本地用户）： 
  
1. Office 应用程序将调用 **IContact.GetContactInformation** 以从联系人获取状态项。 
    
2. 然后，Office 应用程序会订阅联系人的状态更改。 它通过调用 **IContactManager.CreateSubscription** 来获取 [IContactSubscription](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactSubscription) 对象。 它随后会调用 **IContactSubscription.AddContact**，以便将联系人添加到订阅中，然后调用 **IContactSubscription.Subscribe** 以更改联系人的状态。 
    
3. 如果 IM 应用程序支持 **IContact2**，则 Office 将尝试通过调用 **IContact2.BatchGetContactInformation2** 来获取状态信息。
    
4. 然后，Office 应用程序将通过调用 **IContact.BatchGetContactInformation** 来检索联系人的状态属性。 Office 应用程序可以通过访问 **IContact.Settings** 属性来获取第二组状态属性。 
    
5. 最后，Office 应用程序将通过访问 **IContact.CustomGroups** 属性来获取联系人的组成员身份。 这将返回 [IGroupCollection](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IGroup) 集合，其中包含该联系人所属的所有 [IGroup](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IGroup) 对象。 
    
### <a name="disconnecting-from-the-im-application"></a>断开与 IM 应用程序的连接
<a name="off15_IMIntegration_HowConnect"> </a>

当 Office 2013 应用程序检测到来自 IM 应用程序的 **OnShuttingDown** 事件时，它将自动断开连接。 但是，如果 Office 应用程序在 IM 应用程序之前关闭，则 Office 应用程序无法保证已清除连接。 IM 应用程序必须处理客户端连接泄漏。 
  
## <a name="setting-registry-keys-and-entries"></a>设置注册表项
<a name="off15_IMIntegration_SetRegistry"> </a>

如前文所述，支持 IM 的 Office 2013 应用程序会在注册表中查找特定的注册表项、条目和值，以便发现要连接的 IM 客户端应用程序。 这些注册表值为 Office 应用程序提供了类的进程名称和 CLSID，该类充当 IM 客户端应用程序的对象模型（即实现 **IUCOfficeIntegration** 接口的类）的入口点。 Office 应用程序将协同创建该类，并作为客户端连接到 IM 客户端应用程序中的进程外 COM 服务器。 
  
使用表 1 标识必须在注册表中写入的注册表项、条目和值，以将 IM 客户端应用程序与 Office 集成。
  
**表 1. 用于设置默认 IM 客户端应用程序的注册表项**

|**注册表项**|**条目**|**类型**|**值**|**示例**|
|:-----|:-----|:-----|:-----|:-----|
|HKEY_LOCAL_MACHINE\Software\IM Providers\\<Application name\>  <br/> |FriendlyName  <br/> |REG_SZ  <br/> |第三方 IM 客户端应用程序的名称。  <br/> |Litware IM 2012  <br/> |
||ProcessName  <br/> |REG_SZ  <br/> |第三方 IM 客户端应用程序的进程名称。  <br/> |litware.exe  <br/> |
||GUID  <br/> |REG_SZ  <br/> |IM 应用程序中可协同创建的根类的类 ID (CLSID)（实现 **IUCOfficeIntegration** 接口的类）。  <br/> |(A GUID)  <br/> |
|HKEY_CURRENT_USER\Software\IM Providers  <br/> |DefaultIMApp  <br/> |REG_SZ  <br/> |IM 客户端应用程序的名称。 它必须与 HKEY_LOCAL_MACHINE 中的顶层注册表项 (hive) 上的名称相同。  <br/> |Litware  <br/> |
|HKEY_CURRENT_USER\Software\IM Providers\\<Application name\>  <br/> |UpAndRunning  <br/> |REG_DWORD  <br/> | 0 到 2 之间的整数值：  <br/>  0—未运行  <br/>  1—正在启动  <br/>  2—正在运行  <br/> <br/>**注释**：应用程序名称注册表项必须与 DefaultIMApp 条目的值相同。           ||
   
## <a name="implementing-the-required-interfaces-for-integration-with-office"></a>实现与 Office 集成所需的接口
<a name="off15_IMIntegration_ImplementRequired"> </a>

**UCCollaborationLib** 命名空间有三个接口，IM 客户端应用程序的可执行文件（或 COM 服务器）必须实现这些接口，这样才能与 Office 集成。 如果未实现这些接口，则 Office 应用程序将在初始化过程中退出，并且不会与 IM 客户端应用程序建立连接。 
  
所需的接口如下所示：
  
- [IUCOfficeIntegration](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IUCOfficeIntegration) — 虽然不是必需的，但是 **_IUCOfficeIntegrationEvents** 接口也应该在同一个派生类中实现。 
    
- [ILyncClient](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ILyncClient) — 虽然不是必需的，但是 **_ILyncClientEvents** 接口也应该在同一个派生类中实现。 
    
- [IAutomation](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IAutomation)
    
### <a name="iucofficeintegration-interface"></a>IUCOfficeIntegration 接口
<a name="off15_IMIntegration_ImplementRequired_IUCOfficeIntegration"> </a>

**IUCOfficeIntegration** 接口提供用于将 Office 应用程序连接到 IM 客户端应用程序的入口点。 作为启动与 IM 客户端应用程序进行连接的过程的一部分。该接口定义了 Office 应用程序调用的三种方法。 实现 **IUCOfficeIntegration** 接口的类必须是可协同创建的类，这样 Office 才能协同创建它的实例。 此外，它还必须公开在 HKEY_LOCAL_MACHINE\Software\IM Providers\  _Application name_ 注册表项中作为 GUID 条目值输入的 CLSID。 
  
从 **IUCOfficeIntegration** 继承的类也应该实现 **_IUCOfficeIntegrationEvents** 接口。 **_IUCOfficeIntegrationEvents** 接口包含用于公开 **IUCOfficeIntegration** 接口的事件处理程序的成员。 
  
表 2 显示必须在继承自 **IUCOfficeIntegration** 和 **_IUCOfficeIntegration** 的类中实现的成员。
  
> [!NOTE]
> 有关 **IUCOfficeIntegration** 和 **_IUCOfficeIntegrationEvents** 接口及其成员的详细信息，请参阅 [UCCollaborationLib.IUCOfficeIntegration](https://msdn.microsoft.com/library/UCCollaborationLib.IUCOfficeIntegration) 和 [UCCollaborationLib._IUCOfficeIntegrationEvents](https://msdn.microsoft.com/library/UCCollaborationLib._IUCOfficeIntegrationEvents)。 
  
**表 2. IUCOfficeIntegration 和 _IUCOfficeIntegrationEvents 接口的实现**

|**接口**|**成员**|**说明**|
|:-----|:-----|:-----|
|**IUCOfficeIntegration** <br/> |**GetAuthenticationInfo** 方法  <br/> |获取身份验证信息字符串。  <br/> |
||**GetInterface** 方法  <br/> |获取特定版本的接口。  <br/> |
||**GetSupportedFeatures** 方法  <br/> |获取受支持的 Office 集成功能。  <br/> |
|**_IUCOfficeIntegrationEvents** <br/> |**OnShuttingDown** 事件  <br/> |当 IM 客户端应用程序尝试关闭时引发的事件。  <br/> |
   
使用以下代码定义从 IM 客户端应用程序中的 **IUCOfficeIntegration** 和 **_IUCOfficeIntegration** 接口继承的类。 
  
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

**GetAuthenticationInfo** 方法将字符串作为 _version_ 参数的自变量。 当 Office 应用程序调用此方法时，它会传入自变量的两个字符串之一，具体取决于 Office 的版本。 当 Office 应用程序为该方法提供 IM 客户端应用程序支持的 Office 版本（即支持该功能）时，**GetAuthenticationInfo** 方法将返回硬编码的 XML 字符串`<authenticationinfo>`。 
  
使用以下代码在 IM 客户端应用程序代码中实现 **GetAuthentication** 方法。 
  
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

**GetInterface** 方法会将对类的引用传递给调用代码，具体取决于作为 _interface_ 参数的自变量传入的内容。 当 Office 应用程序调用 **GetInterface** 方法时，它会传入接口参数的两个值之一：[UCCollaborationLib.OIInterface](https://msdn.microsoft.com/library/UCCollaborationLib.OIInterface) 枚举的 **oiInterfaceILyncClient** 常量 (1) 或 **oiInterfaceIAutomation** 常量 (2)。 如果 Office 应用程序传入 **oiInterfaceILyncClient** 常量，则 **GetInterface** 方法将返回对实现 **ILyncClient** 接口的类的引用。 如果 Office 应用程序传入 **oiInterfaceIAutomation** 常量，则 **GetInterface** 方法将返回对实现 **IAutomation** 接口的类的引用。 
  
使用以下代码示例在 IM 客户端应用程序代码中实现 **GetInterface** 方法。 
  
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

**GetSupportedFeatures** 方法返回有关 IM 客户端应用程序支持的 IM 功能的信息。 它为其唯一参数 _version_ 使用字符串。 当 Office 应用程序调用 **GetSupportFeatures** 方法时，该方法将返回 [UCCollaborationLib.OIFeature](https://msdn.microsoft.com/library/UCCollaborationLib.OIFeature) 枚举中的值。 返回的值用于指定 IM 客户端的功能，系统通过向此值添加标记，为 IM 应用程序指明 IM 客户端应用程序的每项功能。 
  
> [!NOTE]
>  Office 2013 应用程序将忽略 **OIFeature** 枚举中的以下常量： 
> - **oiFeaturePictures** (2) 
> - **oiFeatureFreeBusyIntegration**
> - **oiFeaturePhoneNormalization**
  
使用以下代码示例在 IM 客户端应用程序代码中实现 **GetSupportFeatures** 方法。 
  
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

**ILyncClient** 接口将映射到 IM 客户端应用程序本身的功能。 它公开了引用登录到应用程序的用户（即本地用户，由 [UCCollaborationLib.ISelf](https://msdn.microsoft.com/library/UCCollaborationLib.ISelf) 接口表示）的属性、应用程序的状态、本地用户的联系人列表以及某些其他设置。 当它尝试连接到 IM 客户端应用程序时，Office 应用程序会获取对实现 **ILyncClient** 接口的对象的引用。 Office 可以从该引用中访问 IM 客户端应用程序的大部分功能。 
  
此外，实现 **ILyncClient** 接口的类还应实现 **_ILyncClientEvents** 接口。 **_ILyncClientEvents** 接口公开了监视 IM 客户端应用程序状态所需的几个事件。 
  
表 3 显示必须在继承自 **ILyncClient** 和 **_ILyncClientEvents** 的类中实现的成员。
  
> [!NOTE]
> 表中未列出的 **ILyncClient** 或 **\_ILyncClientEvents** 接口的任何成员都必须存在，但不需要实现。 存在但未实现的成员可能会引发 **NotImplementedException** 或 **E\_NOTIMPL** 错误。 
> 
> 有关 **ILyncClient** 和 **_ILyncClientEvents** 接口及其成员的详细信息，请参阅 [UCCollaborationLib.ILyncClient](https://msdn.microsoft.com/library/UCCollaborationLib.ILyncClient) 和 [UCCollaborationLib._ILyncClientEvents](https://msdn.microsoft.com/library/UCCollaborationLib._ILyncClientEvents)。 
  
**表 3. ILyncClient 和 ILyncClientEvents 接口的实现**

|**接口**|**成员**|**说明**|
|:-----|:-----|:-----|
|**ILyncClient** <br/> |**ContactManager** 属性  <br/> |获取联系人组管理器。  <br/> |
||**ConversationManager** 属性  <br/> |获取对话管理器。  <br/> |
||**Self** 属性  <br/> |获取 **Self** 对象。  <br/> |
||**SignIn** 方法  <br/> |以特定状态启动 IM 客户端应用程序登录过程。  <br/> |
||**State** 属性  <br/> |获取当前平台状态。  <br/> |
||**Uri** 属性  <br/> |获取 IM 客户端应用程序的 URI。  <br/> |
|**_ILyncClientEvents** <br/> |**OnStateChanged** 事件  <br/> |当 IM 客户端应用程序状态更改时引发。 你应该处理此事件并获取 **eventData.NewState** 属性。 当应用程序中的任何子系统导致状态更改时，将为绑定到 IM 客户端应用程序实例的所有进程引发该事件。  <br/> |
   
在初始化过程中，Office 将访问 **ILyncClient.State** 属性。 此属性需要从 [UCCollaborationLib.ClientState](https://msdn.microsoft.com/library/UCCollaborationLib.ClientState) 枚举中返回一个值。 
  
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

**State** 属性用于存储 IM 客户端应用程序的当前状态。 必须在整个 IM 客户端应用程序会话中设置和更新它。 当 IM 客户端应用程序登录、注销或关闭时，应设置 **State** 属性。 最好在 **ILyncClient.SignIn** 和 **ILyncClient.SignOut** 方法中设置此属性，如以下示例所示。 
  
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

以下代码示例演示如何使用 **_ILyncClientEvents** 和 **_IUCOfficeIntegrationEvents** 接口设置事件侦听器。 
  
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

**IAutomation** 接口用于自动化 IM 客户端应用程序的功能。 它可用于启动对话、加入会议以及提供可扩展性窗口上下文。 
  
表 4 显示必须在继承自 **IAutomation** 的类中实现的成员。
  
> [!NOTE]
> 表中未列出的 **IAutomation** 接口的任何成员都必须存在，但不需要实现。 存在但未实现的成员可能会引发 **NotImplementedException** 或 **E_NOTIMPL** 错误。 
> 
> 有关 **IAutomation** 接口及其成员的详细信息，请参阅 [UCCollaborationLib.IAutomation](https://msdn.microsoft.com/library/UCCollaborationLib.IAutomation)。 
  
**表 4. IAutomation 接口的实现**

|**成员**|**说明**|
|:-----|:-----|
|**StartConversation** 方法  <br/> |使用指定的对话模态启动对话。 将返回 **IConversationWindow** 的实例。  <br/> |
   
## <a name="implementing-contact-presence-integration"></a>实现联系人状态集成
<a name="off15_IMIntegration_ImplementIMFeatures"> </a>

除了前面讨论的三个必需接口之外，还有一些其他接口对于在 Office 中启用联系人状态功能非常重要。 其中包括以下项：
  
- [IContact](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContact) 或 **IContact2** 接口。 
    
- [ISelf](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ISelf) 接口。 
    
- [IContactManager](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactManager) 和 [_IContactManagerEvents](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactManager) 接口。 
    
- [IGroup](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IGroup) 和 [IGroupCollection](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IGroup) 接口。 
    
- [IContactSubscription](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactSubscription) 接口。 
    
- [IContactEndPoint](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactEndPoint) 接口。 
    
- [ILocaleString](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ILocaleString) 接口 
    
### <a name="icontact-interface"></a>IContact 接口
<a name="off15_IMIntegration_ImplementRequired_IContact"> </a>

**IContact** 接口表示 IM 客户端应用程序用户。 该接口将公开用户的状态、可用模态、组成员资格和联系人类型属性。 要与其他用户开始对话，你必须提供 **IContact** 的用户实例。
  
表 5 显示必须在继承自 **IContact** 的类中实现的成员。
  
> [!NOTE]
> 表中未列出的 **IContact** 接口的任何成员都必须存在，但不需要实现。 存在但未实现的成员可能会引发 **NotImplementedException** 或 **E_NOTIMPL** 错误。 
>
> 有关 **IContact** 接口及其成员的详细信息，请参阅 [UCCollaborationLib.IContact](https://msdn.microsoft.com/library/UCCollaborationLib.IContact)。 
  
**表 5. IContact 接口的实现**

|**成员**|**说明**|
|:-----|:-----|
|**CanStart** 方法  <br/> |如果可以在联系人上启动给定类型的模态，则返回 **true**。  <br/> |
|**GetContactInformation** 方法  <br/> |从发布联系人获取一个状态项。  <br/> |
|**BatchGetContactInformation** 方法  <br/> |从发布联系人获取多个状态项。  <br/> |
|**Settings** 属性  <br/> |获取联系人属性的集合。  <br/> |
|**CustomGroups** 属性  <br/> |获取联系人所属的组的集合。  <br/> |
   
在初始化过程中，Office 应用程序通过调用 **IContact.CanStart** 方法来确定本地用户具有的 IM 功能。 **CanStart** 方法从 [UCCollaborationLib.ModalityTypes](https://msdn.microsoft.com/library/UCCollaborationLib.ModalityTypes) 枚举中获取一个标记作为 __modalityTypes_ 参数的自变量。 如果当前用户可以参与所请求的模态（即用户能够进行即时消息传递、音频和视频消息传递或应用程序共享），则 **CanStart** 方法将返回 **true**。
  
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

**GetContactInformation** 方法从 **IContact** 对象检索有关联系人的信息。 调用代码需要从 __contactInformationType_ 参数的 [UCCollaborationLib.ContactInformationType](https://msdn.microsoft.com/library/UCCollaborationLib.ContactInformationType) 枚举中传入一个值，该参数指示要检索的数据。 
  
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

与 **GetContactInformation** 类似，**BatchGetContactInformation** 方法从 **IContact** 对象检索有关联系人的多个状态项。 调用代码需要从 __contactInformationTypes_ 参数的 **ContactInformationType** 枚举中传入一个值数组。 该方法返回包含请求数据的 [UCCollaborationLib.IContactInformationDictionary](https://msdn.microsoft.com/library/UCCollaborationLib.IContactInformationDictionary) 对象。 
  
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

**IContact.Settings** 属性返回 **IContactSettingDictionary** 对象，其中包含有关联系人的自定义属性。 
  
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

**IContact.CustomGroups** 属性返回 **IGroupCollection** 对象，其中包含联系人所属的所有组。 
  
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

在初始化过程中，Office 应用程序通过访问 **ILyncClient.Self** 属性来获取当前用户的数据，该属性必须返回 **ISelf** 对象。 **ISelf** 接口表示本地登录的 IM 客户端应用程序用户。 
  
表 6 显示必须在继承自 **ISelf** 的类中实现的成员。
  
> [!NOTE]
> 表中未列出的 **ISelf** 接口的任何成员都必须存在，但不需要实现。 存在但未实现的成员可能会引发 **NotImplementedException** 或 **E_NOTIMPL** 错误。 
  
**表 6. ISelf 接口的实现**

|**成员**|**说明**|
|:-----|:-----|
|**Contact** 属性  <br/> |获取与本地用户关联的 **IContact** 对象。  <br/> |
   
通过 **ISelf.Contact** 属性（返回 **IContact** 对象）公开本地用户的状态、可用模态、组成员资格和联系人类型属性。 在初始化过程中，Office 应用程序通过访问 **ISelf.Contact** 属性来获取对本地用户的联系信息的引用。 
  
使用以下代码定义从实现 **Contact** 属性的 **ISelf** 接口继承的类。 
  
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

**IContactManager** 对象用于管理本地用户的联系人，包括本地用户自己的联系信息。 Office 应用程序使用 **IContactManager** 对象来访问与本地用户的联系人对应的 **IContact** 对象。 
  
表 7 显示必须在继承自 **IContactManager** 和 **_IContactManagerEvents** 的类中实现的成员。
  
> [!NOTE]
> 表中未列出的 **IContactManager** 接口的任何成员都必须存在，但不需要实现。 存在但未实现的成员可能会引发 **NotImplementedException** 或 **E\_NOTIMPL** 错误。 
>
> 有关 **IContactManager** 和 **_IContactManagerEvents** 接口及其成员的详细信息，请参阅 [UCCollaborationLib.IContactManager](https://msdn.microsoft.com/library/UCCollaborationLib.IContactManager) 和 [UCCollaborationLib._IContactManagerEvents](https://msdn.microsoft.com/library/UCCollaborationLib._IContactManagerEvents)。 
  
**表 7. IContactManager 和 _IContactManagerEvents 接口的实现**

|**接口**|**成员**|**说明**|
|:-----|:-----|:-----|
|**IContactManager** <br/> |**GetContactByUri** 方法  <br/> |使用联系人 URI 查找或创建新的联系人实例。  <br/> |
||**CreateSubscription** 方法  <br/> |创建可用于批量订阅或查询的 **ISubscription** 对象。  <br/> |
||**Lookup** 方法  <br/> |查找联系人或通讯组。  <br/> |
|**_IContactManagerEvents** <br/> |**OnGroupAdded** 事件  <br/> |将组添加到组集合时引发。 可以从 **IContactManager.Groups** 属性获取更新的组集合。  <br/> |
||**OnGroupRemoved** 事件  <br/> |从组集合中删除组时引发。 可以从 **IContactManager.Groups** 属性获取更新的组集合。  <br/> |
||**OnSearchProviderStateChanged** 事件  <br/> |在搜索提供程序的状态更改时引发。  <br/> |
   
Office 通过使用联系人的 SIP 地址来调用 **IContactManager.GetContactByUri**，以便获取联系人的状态信息。 在 Active Directory 中为联系人配置 SIP 地址时，Office 会为联系人确定此地址并调用 **GetContactByUri**，以便将联系人的 SIP 地址传递给 __contactUri_ 参数。 
  
如果 Office 无法确定联系人的 SIP 地址，它会调用 **IContactManager.Lookup** 方法以使用 IM 服务来查找 SIP。 Office 将在此处传入可以为联系人找到的最佳数据（例如，仅联系人的电子邮件地址）。 **Lookup** 方法通过异步方式返回 **AsynchronousOperation** 对象。 当它调用回调时，除了联系人的 URI 之外，**Lookup** 方法应该还会返回操作的成功或失败信息。 
  
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

Office 应用程序需要订阅各个联系人的状态更改。 因此，当联系人的当前状态发生更改时，IM 服务器会向 IM 客户端应用程序发出警报，从而向 Office 应用程序发出警报。 为此，Office 应用程序将调用 **IContactManager.CreateSubscription** 方法，以便为此请求创建新的 **IContactSubscription** 对象。 
  
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

**IGroup** 对象表示具有附加属性的联系人集合，用于通过集合组名称标识联系人集合。 **IGroupCollection** 对象表示由本地用户和 IM 客户端应用程序定义的 **IGroup** 对象的集合。 Office 应用程序使用 **IGroupCollection** 和 **IGroup** 对象来访问本地用户的联系人。 
  
表 9 显示必须在继承自下表中的 **IGroup** 和 **IGroupCollection** 的类中实现的成员。 
  
> [!NOTE]
> 表中未列出的 **IGroup** 接口的任何成员都必须存在，但不需要实现。 存在但未实现的成员可能会引发 **NotImplementedException** 或 **E_NOTIMPL** 错误。 
>
> 有关 **IGroup** 和 **IGroupCollection** 接口及其成员的详细信息，请参阅 [UCCollaborationLib.IGroup](https://msdn.microsoft.com/library/UCCollaborationLib.IGroup) 和 [UCCollaborationLib.IGroupCollection](https://msdn.microsoft.com/library/UCCollaborationLib.IGroupCollection)。 
  
**表 9. IGroup 和 IGroupCollection 接口的实现**

|**接口**|**成员**|**说明**|
|:-----|:-----|:-----|
|**IGroupCollection** <br/> |**Count** 属性  <br/> |返回集合中的 **IGroup** 对象的计数  <br/> |
||**Item** 属性  <br/> |返回集合中指定索引处的 **IGroup** 对象。  <br/> |
|**IGroup** <br/> |**Id** 属性  <br/> |返回组 ID。  <br/> |
   
当 Office 应用程序获取本地用户的信息时，它通过调用 **IContact.CustomGroups** 属性来访问联系人（本地用户）的组成员身份，该属性返回 **IGroupCollection** 对象。 **IGroupCollection** 必须包含 **IGroup** 对象的数组（或 **List**）。 派生自 **IGroupCollection** 的类必须公开 **Count** 属性（它返回集合中的项目数）和索引器方法 **this(int)**（它返回集合中的 **IGroup** 对象）。 
  
### <a name="icontactsubscription-interface"></a>IContactSubscription 接口
<a name="off15_IMIntegration_ImplementRequired_IContactSubscription"> </a>

**IContactSubscription** 接口允许你指定接收状态信息更新的联系人以及触发通知的状态信息类型。 Office 应用程序使用 **IContactSubscription** 对象来注册对联系人状态的更改。 
  
表 10 显示必须在继承自 **IContactSubscription** 的类中实现的成员。
  
> [!NOTE]
> 表中未列出的 **IContactSubscription** 接口的任何成员都必须存在，但不需要实现。 存在但未实现的成员可能会引发 **NotImplementedException** 或 **E_NOTIMPL** 错误。
>
> 有关 **IContactSubscription** 接口及其成员的详细信息，请参阅 [UCCollaborationLib.IContactSubscription](https://msdn.microsoft.com/library/UCCollaborationLib.IContactSubscription)。 
  
**表 10. IContactSubscription 接口的实现**

|**成员**|**说明**|
|:-----|:-----|
|**AddContact** 方法  <br/> |将联系人添加到订阅对象。  <br/> |
|**Subscribe** 方法  <br/> |帮助 IM 客户端应用程序监视联系人的状态。  <br/> |
   
**IContactSubscription** 接口必须包含对其监视的所有 **IContact** 对象的引用（使用数组或 **List**）。 **IContactSubscription.AddContact** 方法为 **IContactSubscription** 对象的基础数据结构添加 **IContact**对象，以便添加要监视状态更改的新联系人。 
  
```cs
// Store references to all of the IContact objects to subscribe to.
private List<IMClientContact> _subscribedContacts;
// Add a new IContact object to the collection of contacts.
public void AddContact(IMClientContact _contact)
{
    this._subscribedContacts.Add(_contact);
}
```

**IContactSubscription.Subscribe** 方法允许 IM 客户端应用程序访问联系人的状态观察者。 它可以使用轮询策略从服务器获取 IM 客户端应用程序订阅的联系人的状态。 如果要请求用户联系人列表之外的联系人（例如，来自更大公共网络的联系人）的状态，则 **Subscribe** 方法非常有用。 
  
### <a name="icontactendpoint-interface"></a>IContactEndPoint 接口
<a name="off15_IMIntegration_ImplementRequired_IContactEndPoint"> </a>

**IContactEndPoint** 表示联系人电话号码集中的电话号码。 
  
表 11 显示必须在继承自 **IContactEndPoint** 的类中实现的成员。
  
> [!NOTE]
> 表中未列出的 **IContactEndPoint** 接口的任何成员都必须存在，但不需要实现。 存在但未实现的成员可能会引发 **NotImplementedException** 或 **E_NOTIMPL** 错误。
>
> 有关 **IContactEndPoint** 接口及其成员的详细信息，请参阅 [UCCollaborationLib.IContactEndpoint](https://msdn.microsoft.com/library/UCCollaborationLib.IContactEndpoint)。 
  
**表 11. IContactEndPoint 接口的实现**

|**成员**|**说明**|
|:-----|:-----|
|**DisplayName** 属性  <br/> |获取显示字符串。  <br/> |
|**Type** 属性  <br/> |获取联系人端点类型  <br/> |
|**Uri** 属性  <br/> |获取联系人 URI。  <br/> |
   
### <a name="ilocalestring-interface"></a>ILocaleString 接口
<a name="off15_IMIntegration_ImplementRequired_ILocaleString"> </a>

**ILocaleString** 是本地化的字符串结构，包含本地化字符串和本地化的区域设置 ID。 **ILocaleString** 接口用于格式化联系人卡片上的自定义状态字符串。 
  
表 12 显示必须在继承自 **ILocaleString** 的类中实现的成员。
  
> [!NOTE]
> 表中未列出的 **ILocaleString** 接口的任何成员都必须存在，但不需要实现。 存在但未实现的成员可能会引发 **NotImplementedException** 或 **E_NOTIMPL** 错误。
>
> 有关 **ILocalString** 接口及其成员的详细信息，请参阅 [UCCollaborationLib.ILocaleString](https://msdn.microsoft.com/library/UCCollaborationLib.ILocaleString)。 
  
**表 12. ILocaleString 接口的实现**

|**成员**|**说明**|
|:-----|:-----|
|**LocaleId** 属性  <br/> |获取区域设置 ID。  <br/> |
|**Value** 属性  <br/> |获取字符串。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [UCCollaborationLib](https://msdn.microsoft.com/library/UCCollaborationLib) 命名空间 
    

