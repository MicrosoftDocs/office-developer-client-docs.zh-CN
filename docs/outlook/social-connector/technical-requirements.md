---
title: 技术要求
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: eff6d5d6-8855-4e54-a781-9deab8cc0aca
description: 本主题介绍支持的编程语言、COM 可见性和方法返回类型要求，以及 OSC Outlook (OSC) DLL 的详细信息。
ms.openlocfilehash: 14dfcf52d714177775c5610b5da91d174f81a132
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329153"
---
# <a name="technical-requirements"></a><span data-ttu-id="a6e3f-103">技术要求</span><span class="sxs-lookup"><span data-stu-id="a6e3f-103">Technical requirements</span></span>

<span data-ttu-id="a6e3f-104">本主题介绍支持的编程语言、COM 可见性和方法返回类型要求，以及 OSC Outlook (OSC) DLL 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a6e3f-104">This topic describes the supported programming languages, COM visibility and method return type requirements, and details of the Outlook Social Connector (OSC) provider extensibility DLL.</span></span> 
  
## <a name="programming-language-and-com-requirements"></a><span data-ttu-id="a6e3f-105">编程语言和 COM 要求</span><span class="sxs-lookup"><span data-stu-id="a6e3f-105">Programming language and COM requirements</span></span>

<span data-ttu-id="a6e3f-106">可以使用托管语言（如 Visual C# 或 Visual Basic）或非托管语言（如 Visual C++）创建 OSC 提供程序。</span><span class="sxs-lookup"><span data-stu-id="a6e3f-106">You can create an OSC provider by using managed languages such as Visual C# or Visual Basic, or unmanaged languages such as Visual C++.</span></span> <span data-ttu-id="a6e3f-107">可以使用任何可以创建 COM 可见的 DLL 组件的工具来开发 OSC 提供程序。</span><span class="sxs-lookup"><span data-stu-id="a6e3f-107">You can use any tool that can create a COM-visible DLL component to develop an OSC provider.</span></span> <span data-ttu-id="a6e3f-108">决定使用托管语言还是非托管语言来开发提供程序时，应当考虑提供程序安装程序包的下载大小和依赖项。</span><span class="sxs-lookup"><span data-stu-id="a6e3f-108">The decision to use a managed or unmanaged language to develop a provider should take into account the download size and dependencies of the provider installation package.</span></span>
  
<span data-ttu-id="a6e3f-109">OSC 提供程序必须是 COM 可见的，如以下内容所定义：</span><span class="sxs-lookup"><span data-stu-id="a6e3f-109">An OSC provider must be COM-visible as defined by the following:</span></span>
  
- <span data-ttu-id="a6e3f-110">安装后，必须使用 COM 自注册或 regsvr32 注册 OSC 提供程序。</span><span class="sxs-lookup"><span data-stu-id="a6e3f-110">After installation, an OSC provider must be registered by using COM self-registration or regsvr32.</span></span>
    
- <span data-ttu-id="a6e3f-111">OSC 提供程序 DLL 的 COM 注册在 HKCU 或 HKLM 下注册提供商。</span><span class="sxs-lookup"><span data-stu-id="a6e3f-111">COM registration of an OSC provider DLL registers the provider under HKCU or HKLM.</span></span> 
    
- <span data-ttu-id="a6e3f-112">提供程序的 ProgID 注册在  `HKCU\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders` 下。</span><span class="sxs-lookup"><span data-stu-id="a6e3f-112">A provider's ProgID is registered under  `HKCU\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders`.</span></span>
    
- <span data-ttu-id="a6e3f-113">使用托管语言开发的 OSC 提供程序是 COM 可见的。</span><span class="sxs-lookup"><span data-stu-id="a6e3f-113">An OSC provider developed in a managed language is COM-visible.</span></span>
    
- <span data-ttu-id="a6e3f-114">OSC 提供程序应向 Windows 注册表添加值，指示提供程序 DLL 支持单线程单元 (STA) 和多线程单元 (MTA) 模型。</span><span class="sxs-lookup"><span data-stu-id="a6e3f-114">An OSC provider should add values to the Windows registry that indicate that the provider DLL supports both single-threaded apartment (STA) and multithreaded apartment (MTA) threading models.</span></span> <span data-ttu-id="a6e3f-115">有关 COM 线程模型详细信息，请参阅[OLE 线程模型的说明和工作。](https://support.microsoft.com/kb/150777)</span><span class="sxs-lookup"><span data-stu-id="a6e3f-115">For more information about COM threading models, see [Descriptions and Workings of OLE Threading Models](https://support.microsoft.com/kb/150777).</span></span>
    
<span data-ttu-id="a6e3f-116">OSC 提供程序扩展性中的方法必须返回基元类型，如 **字符串** 或 **布尔值**。</span><span class="sxs-lookup"><span data-stu-id="a6e3f-116">Methods in OSC provider extensibility must return primitive types such as **string** or **bool**.</span></span> <span data-ttu-id="a6e3f-117">某些 **字符串** 返回值必须符合 OSC 提供程序扩展性架构定义。</span><span class="sxs-lookup"><span data-stu-id="a6e3f-117">Certain **string** return values must comply with the schema definition for OSC provider extensibility.</span></span> <span data-ttu-id="a6e3f-118">仅支持 XML 作为返回值。</span><span class="sxs-lookup"><span data-stu-id="a6e3f-118">Only XML is supported as a return value.</span></span> 
  
## <a name="details-of-the-osc-provider-extensibility-dll"></a><span data-ttu-id="a6e3f-119">OSC 提供程序扩展 DLL 的详细信息</span><span class="sxs-lookup"><span data-stu-id="a6e3f-119">Details of the OSC provider extensibility DLL</span></span>

<span data-ttu-id="a6e3f-120">支持 OSC 提供程序扩展性的组件是 OSC 提供程序扩展 DLL。</span><span class="sxs-lookup"><span data-stu-id="a6e3f-120">The component that supports OSC provider extensibility is the OSC provider extensibility DLL.</span></span> <span data-ttu-id="a6e3f-121">第三方开发人员可以使用这些扩展性接口生成 OSC 提供程序 DLL。</span><span class="sxs-lookup"><span data-stu-id="a6e3f-121">Third-party developers can build OSC provider DLLs by using these extensibility interfaces.</span></span> <span data-ttu-id="a6e3f-122">以下列表显示了 OSC 提供程序扩展 DLL 的详细信息：</span><span class="sxs-lookup"><span data-stu-id="a6e3f-122">The following list shows the details of the OSC provider extensibility DLL:</span></span>
  
- <span data-ttu-id="a6e3f-123">扩展性 DLL 文件名：socialprovider.dll</span><span class="sxs-lookup"><span data-stu-id="a6e3f-123">Extensibility DLL file name: socialprovider.dll</span></span>
    
- <span data-ttu-id="a6e3f-124">扩展性 DLL 友好名称：Microsoft Outlook社交提供程序扩展性</span><span class="sxs-lookup"><span data-stu-id="a6e3f-124">Extensibility DLL friendly name: Microsoft Outlook Social Provider Extensibility</span></span>
    
- <span data-ttu-id="a6e3f-125">扩展性 DLL 主要版本：15.0</span><span class="sxs-lookup"><span data-stu-id="a6e3f-125">Extensibility DLL major version: 15.0</span></span>
    
- <span data-ttu-id="a6e3f-126">Extensibiilty DLL TypeLib 版本：1.1</span><span class="sxs-lookup"><span data-stu-id="a6e3f-126">Extensibiilty DLL TypeLib version: 1.1</span></span>
    
## <a name="miscellaneous-technical-information"></a><span data-ttu-id="a6e3f-127">杂项技术信息</span><span class="sxs-lookup"><span data-stu-id="a6e3f-127">Miscellaneous technical information</span></span>

<span data-ttu-id="a6e3f-128">OSC 提供程序扩展 (不支持 JavaScript (JSON) JSON 对象表示法。</span><span class="sxs-lookup"><span data-stu-id="a6e3f-128">JavaScript Object Notation (JSON) is not supported in the OSC provider extensibility model.</span></span>
  
<span data-ttu-id="a6e3f-129">XML 分析程序上没有任何依赖关系。</span><span class="sxs-lookup"><span data-stu-id="a6e3f-129">There are no dependencies on an XML parser.</span></span> <span data-ttu-id="a6e3f-130">OSC 提供程序可以使用 Office 中包含的 XML 分析程序（如 Microsoft XML Core Services (MSXML)  (MSXML) ）、使用 Microsoft .NET Framework 中内置的 XML 分析功能或使用第三方 XML 分析程序。</span><span class="sxs-lookup"><span data-stu-id="a6e3f-130">The OSC provider can use an XML parser that is included with Office, such as Microsoft XML Core Services (MSXML), use the XML parsing capabilities built into the Microsoft .NET Framework, or use a third-party XML parser.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a6e3f-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a6e3f-131">See also</span></span>

- [<span data-ttu-id="a6e3f-132">开发提供程序的最佳实践</span><span class="sxs-lookup"><span data-stu-id="a6e3f-132">Best Practices for Developing a Provider</span></span>](best-practices-for-developing-a-provider.md)  
- [<span data-ttu-id="a6e3f-133">学习开发提供程序的快速步骤</span><span class="sxs-lookup"><span data-stu-id="a6e3f-133">Quick Steps for Learning to Develop a Provider</span></span>](quick-steps-for-learning-to-develop-a-provider.md)
- [<span data-ttu-id="a6e3f-134">部署提供程序</span><span class="sxs-lookup"><span data-stu-id="a6e3f-134">Deploying a Provider</span></span>](deploying-a-provider.md)  
- [<span data-ttu-id="a6e3f-135">Outlook Social Connector 提供程序开发入门（英文）</span><span class="sxs-lookup"><span data-stu-id="a6e3f-135">Getting Started with Developing an Outlook Social Connector Provider</span></span>](getting-started-with-developing-an-outlook-social-connector-provider.md)

