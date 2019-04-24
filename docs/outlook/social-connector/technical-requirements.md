---
title: 技术要求
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: eff6d5d6-8855-4e54-a781-9deab8cc0aca
description: 本主题介绍了受支持的编程语言、COM 可见性和方法返回类型要求, 以及 Outlook Social Connector (.osc) 提供程序扩展 DLL 的详细信息。
ms.openlocfilehash: 14dfcf52d714177775c5610b5da91d174f81a132
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329153"
---
# <a name="technical-requirements"></a><span data-ttu-id="d8671-103">技术要求</span><span class="sxs-lookup"><span data-stu-id="d8671-103">Technical requirements</span></span>

<span data-ttu-id="d8671-104">本主题介绍了受支持的编程语言、COM 可见性和方法返回类型要求, 以及 Outlook Social Connector (.osc) 提供程序扩展 DLL 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d8671-104">This topic describes the supported programming languages, COM visibility and method return type requirements, and details of the Outlook Social Connector (OSC) provider extensibility DLL.</span></span> 
  
## <a name="programming-language-and-com-requirements"></a><span data-ttu-id="d8671-105">编程语言和 COM 要求</span><span class="sxs-lookup"><span data-stu-id="d8671-105">Programming language and COM requirements</span></span>

<span data-ttu-id="d8671-106">可以使用托管语言 (如 visual c # 或 visual Basic) 或非托管语言 (如 visual c + +) 创建 .osc 提供程序。</span><span class="sxs-lookup"><span data-stu-id="d8671-106">You can create an OSC provider by using managed languages such as Visual C# or Visual Basic, or unmanaged languages such as Visual C++.</span></span> <span data-ttu-id="d8671-107">您可以使用任何可创建 COM 可见的 DLL 组件来开发 .osc 提供程序的工具。</span><span class="sxs-lookup"><span data-stu-id="d8671-107">You can use any tool that can create a COM-visible DLL component to develop an OSC provider.</span></span> <span data-ttu-id="d8671-108">使用托管或非托管语言开发提供程序的决定应考虑提供程序安装包的下载大小和依赖项。</span><span class="sxs-lookup"><span data-stu-id="d8671-108">The decision to use a managed or unmanaged language to develop a provider should take into account the download size and dependencies of the provider installation package.</span></span>
  
<span data-ttu-id="d8671-109">.osc 提供程序必须按以下方式定义的 COM 可见:</span><span class="sxs-lookup"><span data-stu-id="d8671-109">An OSC provider must be COM-visible as defined by the following:</span></span>
  
- <span data-ttu-id="d8671-110">安装完成后, 必须使用 COM 自注册或 regsvr32 注册一个 .osc 提供程序。</span><span class="sxs-lookup"><span data-stu-id="d8671-110">After installation, an OSC provider must be registered by using COM self-registration or regsvr32.</span></span>
    
- <span data-ttu-id="d8671-111">您的 .osc 提供程序 DLL 的 COM 注册会在 HKCU 或 HKLM 下注册提供程序。</span><span class="sxs-lookup"><span data-stu-id="d8671-111">COM registration of an OSC provider DLL registers the provider under HKCU or HKLM.</span></span> 
    
- <span data-ttu-id="d8671-112">提供程序的 ProgID 在`HKCU\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders`中注册。</span><span class="sxs-lookup"><span data-stu-id="d8671-112">A provider's ProgID is registered under  `HKCU\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders`.</span></span>
    
- <span data-ttu-id="d8671-113">在托管语言中开发的一个 .osc 提供程序是 COM 可见的。</span><span class="sxs-lookup"><span data-stu-id="d8671-113">An OSC provider developed in a managed language is COM-visible.</span></span>
    
- <span data-ttu-id="d8671-114">.osc 提供程序应将值添加到 Windows 注册表中, 以指示提供程序 DLL 支持单线程单元 (STA) 和多线程单元 (MTA) 线程模型。</span><span class="sxs-lookup"><span data-stu-id="d8671-114">An OSC provider should add values to the Windows registry that indicate that the provider DLL supports both single-threaded apartment (STA) and multithreaded apartment (MTA) threading models.</span></span> <span data-ttu-id="d8671-115">有关 COM 线程模型的详细信息, 请参阅[OLE 线程模型的说明和工作原理](https://support.microsoft.com/kb/150777)。</span><span class="sxs-lookup"><span data-stu-id="d8671-115">For more information about COM threading models, see [Descriptions and Workings of OLE Threading Models](https://support.microsoft.com/kb/150777).</span></span>
    
<span data-ttu-id="d8671-116">.osc 提供程序扩展性中的方法必须返回基元类型, 如**string**或**bool**。</span><span class="sxs-lookup"><span data-stu-id="d8671-116">Methods in OSC provider extensibility must return primitive types such as **string** or **bool**.</span></span> <span data-ttu-id="d8671-117">某些**字符串**返回值必须符合 .osc 提供程序可扩展性的架构定义。</span><span class="sxs-lookup"><span data-stu-id="d8671-117">Certain **string** return values must comply with the schema definition for OSC provider extensibility.</span></span> <span data-ttu-id="d8671-118">仅支持 XML 作为返回值。</span><span class="sxs-lookup"><span data-stu-id="d8671-118">Only XML is supported as a return value.</span></span> 
  
## <a name="details-of-the-osc-provider-extensibility-dll"></a><span data-ttu-id="d8671-119">.osc 提供程序扩展性 DLL 的详细信息</span><span class="sxs-lookup"><span data-stu-id="d8671-119">Details of the OSC provider extensibility DLL</span></span>

<span data-ttu-id="d8671-120">支持 .osc 提供程序可扩展性的组件是 .osc 提供程序扩展性 DLL。</span><span class="sxs-lookup"><span data-stu-id="d8671-120">The component that supports OSC provider extensibility is the OSC provider extensibility DLL.</span></span> <span data-ttu-id="d8671-121">第三方开发人员可以使用这些扩展性接口生成 .osc 提供程序 dll。</span><span class="sxs-lookup"><span data-stu-id="d8671-121">Third-party developers can build OSC provider DLLs by using these extensibility interfaces.</span></span> <span data-ttu-id="d8671-122">以下列表显示了 .osc 提供程序扩展性 DLL 的详细信息:</span><span class="sxs-lookup"><span data-stu-id="d8671-122">The following list shows the details of the OSC provider extensibility DLL:</span></span>
  
- <span data-ttu-id="d8671-123">可扩展性 DLL 文件名: socialprovider</span><span class="sxs-lookup"><span data-stu-id="d8671-123">Extensibility DLL file name: socialprovider.dll</span></span>
    
- <span data-ttu-id="d8671-124">可扩展性 DLL 友好名称: Microsoft Outlook Social Provider 扩展性</span><span class="sxs-lookup"><span data-stu-id="d8671-124">Extensibility DLL friendly name: Microsoft Outlook Social Provider Extensibility</span></span>
    
- <span data-ttu-id="d8671-125">可扩展性 DLL 主要版本: 15。0</span><span class="sxs-lookup"><span data-stu-id="d8671-125">Extensibility DLL major version: 15.0</span></span>
    
- <span data-ttu-id="d8671-126">Extensibiilty DLL TypeLib 版本: 1。1</span><span class="sxs-lookup"><span data-stu-id="d8671-126">Extensibiilty DLL TypeLib version: 1.1</span></span>
    
## <a name="miscellaneous-technical-information"></a><span data-ttu-id="d8671-127">其他技术信息</span><span class="sxs-lookup"><span data-stu-id="d8671-127">Miscellaneous technical information</span></span>

<span data-ttu-id="d8671-128">在 .osc 提供程序扩展性模型中不支持 JavaScript 对象表示法 (JSON)。</span><span class="sxs-lookup"><span data-stu-id="d8671-128">JavaScript Object Notation (JSON) is not supported in the OSC provider extensibility model.</span></span>
  
<span data-ttu-id="d8671-129">XML 分析程序没有任何依赖项。</span><span class="sxs-lookup"><span data-stu-id="d8671-129">There are no dependencies on an XML parser.</span></span> <span data-ttu-id="d8671-130">.osc 提供程序可以使用 Office 附带的 xml 分析程序 (如 microsoft XML Core Services (MSXML)), 使用 microsoft .net Framework 中内置的 xml 分析功能, 或使用第三方 xml 分析器。</span><span class="sxs-lookup"><span data-stu-id="d8671-130">The OSC provider can use an XML parser that is included with Office, such as Microsoft XML Core Services (MSXML), use the XML parsing capabilities built into the Microsoft .NET Framework, or use a third-party XML parser.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d8671-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d8671-131">See also</span></span>

- [<span data-ttu-id="d8671-132">开发提供程序的最佳实践</span><span class="sxs-lookup"><span data-stu-id="d8671-132">Best Practices for Developing a Provider</span></span>](best-practices-for-developing-a-provider.md)  
- [<span data-ttu-id="d8671-133">学习开发提供程序的快速步骤</span><span class="sxs-lookup"><span data-stu-id="d8671-133">Quick Steps for Learning to Develop a Provider</span></span>](quick-steps-for-learning-to-develop-a-provider.md)
- [<span data-ttu-id="d8671-134">部署提供程序</span><span class="sxs-lookup"><span data-stu-id="d8671-134">Deploying a Provider</span></span>](deploying-a-provider.md)  
- [<span data-ttu-id="d8671-135">Outlook Social Connector 提供程序开发入门（英文）</span><span class="sxs-lookup"><span data-stu-id="d8671-135">Getting Started with Developing an Outlook Social Connector Provider</span></span>](getting-started-with-developing-an-outlook-social-connector-provider.md)

