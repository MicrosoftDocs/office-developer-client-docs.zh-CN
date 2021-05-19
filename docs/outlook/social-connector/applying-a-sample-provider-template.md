---
title: 应用示例提供程序模板
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: da487569-f2f0-404c-b944-38ed1c1b82bb
description: '使用 OSC Outlook连接器 (OSC) 模板的示例为您提供了一个实现 OSC 提供程序的框架。 '
ms.openlocfilehash: 10fb21ab640e298bc655b8cad554fae789e2ad47
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425909"
---
# <a name="applying-a-sample-provider-template"></a><span data-ttu-id="a52bb-103">应用示例提供程序模板</span><span class="sxs-lookup"><span data-stu-id="a52bb-103">Applying a Sample Provider Template</span></span>

<span data-ttu-id="a52bb-104">使用 OSC Outlook连接器 (OSC) 模板的示例为您提供了一个实现 OSC 提供程序的框架。</span><span class="sxs-lookup"><span data-stu-id="a52bb-104">The sample Outlook Social Connector (OSC) provider templates give you a framework for implementing an OSC provider.</span></span> <span data-ttu-id="a52bb-105">提供程序模板以 C++、C# 和 Visual Basic 提供。</span><span class="sxs-lookup"><span data-stu-id="a52bb-105">The provider templates are available in C++, C#, and Visual Basic.</span></span> <span data-ttu-id="a52bb-106">这些模板只是提供程序开发的起点;这些模板不编写提供程序的实现代码和为提供程序创建安装包。</span><span class="sxs-lookup"><span data-stu-id="a52bb-106">These templates are just a starting point for your provider development; the templates do not address writing the implementation code for the provider and creating a setup package for the provider.</span></span> <span data-ttu-id="a52bb-107">以下过程演示如何在开始开发提供程序时应用 OSC 提供程序模板。</span><span class="sxs-lookup"><span data-stu-id="a52bb-107">The following procedure shows how to apply an OSC provider template when you begin to develop a provider.</span></span>
  
### <a name="to-apply-an-osc-provider-template"></a><span data-ttu-id="a52bb-108">应用 OSC 提供程序模板</span><span class="sxs-lookup"><span data-stu-id="a52bb-108">To apply an OSC provider template</span></span>

1. <span data-ttu-id="a52bb-109">在"**开始"** 菜单上，右键单击 **"Microsoft Visual Studio 2010"，** 然后单击"以管理员 **角色运行"** 命令。</span><span class="sxs-lookup"><span data-stu-id="a52bb-109">On the **Start** menu, right-click **Microsoft Visual Studio 2010** and click the **Run as administrator** command.</span></span> <span data-ttu-id="a52bb-110">当系统提示时，单击 **"** 是"Visual Studio管理员运行此配置。</span><span class="sxs-lookup"><span data-stu-id="a52bb-110">When prompted, click **Yes** to run Visual Studio as an administrator.</span></span> 
    
2. <span data-ttu-id="a52bb-111">将模板中的项目名称和命名空间更改为项目名称和命名空间标识符。</span><span class="sxs-lookup"><span data-stu-id="a52bb-111">Change the project name and namespace in the template to your project name and namespace identifiers.</span></span>
    
3. <span data-ttu-id="a52bb-112">修改 **AssemblyInfo** 类以指定相应的程序集信息。</span><span class="sxs-lookup"><span data-stu-id="a52bb-112">Modify the **AssemblyInfo** class to specify the appropriate assembly information.</span></span> 
    
4. <span data-ttu-id="a52bb-113">根据需要实现标记为 **微软待办并** 添加更多依赖项和引用。</span><span class="sxs-lookup"><span data-stu-id="a52bb-113">Implement the interface members marked as **To-Do** and add more dependencies and references, as required.</span></span> 
    
5. <span data-ttu-id="a52bb-114">生成项目。</span><span class="sxs-lookup"><span data-stu-id="a52bb-114">Build the project.</span></span>
    
6. <span data-ttu-id="a52bb-115">确保提供程序程序集 ProgID 在 下作为键列出  `HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders` 。</span><span class="sxs-lookup"><span data-stu-id="a52bb-115">Ensure that the provider assembly ProgID is listed as a key under  `HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders`.</span></span>
    
7. <span data-ttu-id="a52bb-116">若要分发安装项目，请用自己Visual Studio或设置工具创建安装项目。</span><span class="sxs-lookup"><span data-stu-id="a52bb-116">To distribute the setup project, create a setup project in Visual Studio or a setup tool of your choice.</span></span>
    
8. <span data-ttu-id="a52bb-117">安装项目应完成程序集的 COM 注册，并创建步骤 5 中列出的 ProgID 密钥。</span><span class="sxs-lookup"><span data-stu-id="a52bb-117">Your setup project should complete COM registration for your assembly and also create the ProgID key as listed in step 5.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a52bb-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a52bb-118">See also</span></span>

- [<span data-ttu-id="a52bb-119">下载示例</span><span class="sxs-lookup"><span data-stu-id="a52bb-119">Downloading the Samples</span></span>](downloading-the-samples.md)
- [<span data-ttu-id="a52bb-120">OSC 示例模板</span><span class="sxs-lookup"><span data-stu-id="a52bb-120">OSC Sample Templates</span></span>](osc-sample-templates.md)

