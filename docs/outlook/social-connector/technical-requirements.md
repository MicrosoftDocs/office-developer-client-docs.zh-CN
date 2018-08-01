---
title: 技术要求
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: eff6d5d6-8855-4e54-a781-9deab8cc0aca
description: 本主题介绍支持的编程语言，COM 可见性和方法可返回类型要求和 Outlook Social Connector (OSC) 提供程序扩展性 DLL 的详细信息。
ms.openlocfilehash: 94b57e20957f3d8d779c4d3324ecbb8ccd37f60a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779329"
---
# <a name="technical-requirements"></a><span data-ttu-id="706ef-103">技术要求</span><span class="sxs-lookup"><span data-stu-id="706ef-103">Technical requirements</span></span>

<span data-ttu-id="706ef-104">本主题介绍支持的编程语言，COM 可见性和方法可返回类型要求和 Outlook Social Connector (OSC) 提供程序扩展性 DLL 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="706ef-104">This topic describes the supported programming languages, COM visibility and method return type requirements, and details of the Outlook Social Connector (OSC) provider extensibility DLL.</span></span> 
  
## <a name="programming-language-and-com-requirements"></a><span data-ttu-id="706ef-105">编程语言和 COM 要求</span><span class="sxs-lookup"><span data-stu-id="706ef-105">Programming language and COM requirements</span></span>

<span data-ttu-id="706ef-106">您可以通过使用 Visual C# 或 Visual Basic 中，如托管的语言或非托管如 Visual c + + 语言创建 OSC 提供程序。</span><span class="sxs-lookup"><span data-stu-id="706ef-106">You can create an OSC provider by using managed languages such as Visual C# or Visual Basic, or unmanaged languages such as Visual C++.</span></span> <span data-ttu-id="706ef-107">您可以使用任何工具，可以创建一个 COM 可见 DLL 组件来开发 OSC 提供程序。</span><span class="sxs-lookup"><span data-stu-id="706ef-107">You can use any tool that can create a COM-visible DLL component to develop an OSC provider.</span></span> <span data-ttu-id="706ef-108">使用托管或非托管语言，以开发提供程序的决策应考虑到帐户下载大小和提供程序安装程序包的依赖项。</span><span class="sxs-lookup"><span data-stu-id="706ef-108">The decision to use a managed or unmanaged language to develop a provider should take into account the download size and dependencies of the provider installation package.</span></span>
  
<span data-ttu-id="706ef-109">OSC 提供程序必须是 COM 可见，由以下定义：</span><span class="sxs-lookup"><span data-stu-id="706ef-109">An OSC provider must be COM-visible as defined by the following:</span></span>
  
- <span data-ttu-id="706ef-110">安装完成后，必须通过使用 COM 注册或 regsvr32 注册 OSC 提供程序。</span><span class="sxs-lookup"><span data-stu-id="706ef-110">After installation, an OSC provider must be registered by using COM self-registration or regsvr32.</span></span>
    
- <span data-ttu-id="706ef-111">OSC 提供程序 DLL 的 COM 注册注册 HKCU 或 HKLM 下的提供程序。</span><span class="sxs-lookup"><span data-stu-id="706ef-111">COM registration of an OSC provider DLL registers the provider under HKCU or HKLM.</span></span> 
    
- <span data-ttu-id="706ef-112">提供程序的 ProgID 注册下`HKCU\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders`。</span><span class="sxs-lookup"><span data-stu-id="706ef-112">A provider's ProgID is registered under  `HKCU\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders`.</span></span>
    
- <span data-ttu-id="706ef-113">OSC 提供程序托管的语言开发是 COM 可见。</span><span class="sxs-lookup"><span data-stu-id="706ef-113">An OSC provider developed in a managed language is COM-visible.</span></span>
    
- <span data-ttu-id="706ef-114">OSC 提供程序应将值添加到 Windows 注册表的指示提供程序 DLL 支持单线程单元 (STA) 和多线程的单元 (MTA) 线程模型。</span><span class="sxs-lookup"><span data-stu-id="706ef-114">An OSC provider should add values to the Windows registry that indicate that the provider DLL supports both single-threaded apartment (STA) and multithreaded apartment (MTA) threading models.</span></span> <span data-ttu-id="706ef-115">有关 COM 线程模型的详细信息，请参阅[说明和工作原理的 OLE 线程模型](http://support.microsoft.com/kb/150777)。</span><span class="sxs-lookup"><span data-stu-id="706ef-115">For more information about COM threading models, see [Descriptions and Workings of OLE Threading Models](http://support.microsoft.com/kb/150777).</span></span>
    
<span data-ttu-id="706ef-116">OSC 提供程序扩展性中的方法必须返回如**字符串**或**bool**基元类型。</span><span class="sxs-lookup"><span data-stu-id="706ef-116">Methods in OSC provider extensibility must return primitive types such as **string** or **bool**.</span></span> <span data-ttu-id="706ef-117">某些**字符串**返回的值必须遵守 OSC 提供程序扩展性的架构定义。</span><span class="sxs-lookup"><span data-stu-id="706ef-117">Certain **string** return values must comply with the schema definition for OSC provider extensibility.</span></span> <span data-ttu-id="706ef-118">仅 XML 的返回值为支持。</span><span class="sxs-lookup"><span data-stu-id="706ef-118">Only XML is supported as a return value.</span></span> 
  
## <a name="details-of-the-osc-provider-extensibility-dll"></a><span data-ttu-id="706ef-119">OSC 提供程序扩展性 DLL 的详细信息</span><span class="sxs-lookup"><span data-stu-id="706ef-119">Details of the OSC provider extensibility DLL</span></span>

<span data-ttu-id="706ef-120">支持 OSC 提供程序扩展性的组件是 OSC 提供程序扩展性 DLL。</span><span class="sxs-lookup"><span data-stu-id="706ef-120">The component that supports OSC provider extensibility is the OSC provider extensibility DLL.</span></span> <span data-ttu-id="706ef-121">第三方开发人员可以通过使用这些扩展性接口构建 OSC 提供程序 Dll。</span><span class="sxs-lookup"><span data-stu-id="706ef-121">Third-party developers can build OSC provider DLLs by using these extensibility interfaces.</span></span> <span data-ttu-id="706ef-122">以下列表显示了 OSC 提供程序扩展性 DLL 的详细信息：</span><span class="sxs-lookup"><span data-stu-id="706ef-122">The following list shows the details of the OSC provider extensibility DLL:</span></span>
  
- <span data-ttu-id="706ef-123">扩展性 DLL 文件名称： socialprovider.dll</span><span class="sxs-lookup"><span data-stu-id="706ef-123">Extensibility DLL file name: socialprovider.dll</span></span>
    
- <span data-ttu-id="706ef-124">扩展性 DLL 友好名称： Microsoft Outlook 社交提供程序扩展性</span><span class="sxs-lookup"><span data-stu-id="706ef-124">Extensibility DLL friendly name: Microsoft Outlook Social Provider Extensibility</span></span>
    
- <span data-ttu-id="706ef-125">扩展性 DLL 主要版本： 15.0</span><span class="sxs-lookup"><span data-stu-id="706ef-125">Extensibility DLL major version: 15.0</span></span>
    
- <span data-ttu-id="706ef-126">Extensibiilty DLL 类型库的版本： 1.1</span><span class="sxs-lookup"><span data-stu-id="706ef-126">Extensibiilty DLL TypeLib version: 1.1</span></span>
    
## <a name="miscellaneous-technical-information"></a><span data-ttu-id="706ef-127">Miscellaneous 的技术信息</span><span class="sxs-lookup"><span data-stu-id="706ef-127">Miscellaneous technical information</span></span>

<span data-ttu-id="706ef-128">OSC 提供程序扩展性模型中不支持 JavaScript 对象表示法 (JSON)。</span><span class="sxs-lookup"><span data-stu-id="706ef-128">JavaScript Object Notation (JSON) is not supported in the OSC provider extensibility model.</span></span>
  
<span data-ttu-id="706ef-129">XML 分析中没有任何关系。</span><span class="sxs-lookup"><span data-stu-id="706ef-129">There are no dependencies on an XML parser.</span></span> <span data-ttu-id="706ef-130">OSC 提供程序可以使用 XML 分析程序随 Office，如 Microsoft XML Core Services (MSXML)、 使用 XML 分析功能构建到 Microsoft.NET Framework，或使用第三方 XML 分析程序。</span><span class="sxs-lookup"><span data-stu-id="706ef-130">The OSC provider can use an XML parser that is included with Office, such as Microsoft XML Core Services (MSXML), use the XML parsing capabilities built into the Microsoft .NET Framework, or use a third-party XML parser.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="706ef-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="706ef-131">See also</span></span>

- [<span data-ttu-id="706ef-132">开发提供程序的最佳做法</span><span class="sxs-lookup"><span data-stu-id="706ef-132">Best Practices for Developing a Provider</span></span>](best-practices-for-developing-a-provider.md)  
- [<span data-ttu-id="706ef-133">快速学习开发提供程序的步骤</span><span class="sxs-lookup"><span data-stu-id="706ef-133">Quick Steps for Learning to Develop a Provider</span></span>](quick-steps-for-learning-to-develop-a-provider.md)
- [<span data-ttu-id="706ef-134">部署提供程序</span><span class="sxs-lookup"><span data-stu-id="706ef-134">Deploying a Provider</span></span>](deploying-a-provider.md)  
- [<span data-ttu-id="706ef-135">Outlook Social Connector 提供程序开发入门（英文）</span><span class="sxs-lookup"><span data-stu-id="706ef-135">Getting Started with Developing an Outlook Social Connector Provider</span></span>](getting-started-with-developing-an-outlook-social-connector-provider.md)

