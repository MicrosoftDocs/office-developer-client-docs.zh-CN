---
title: 应用示例提供程序模板
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: da487569-f2f0-404c-b944-38ed1c1b82bb
description: '示例 Outlook Social Connector (OSC) 提供程序模板为您提供一个框架，用于实现 OSC 提供程序。 '
ms.openlocfilehash: 2388da58690e1870434c576bfa68649937156c54
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779192"
---
# <a name="applying-a-sample-provider-template"></a><span data-ttu-id="94459-103">应用示例提供程序模板</span><span class="sxs-lookup"><span data-stu-id="94459-103">Applying a Sample Provider Template</span></span>

<span data-ttu-id="94459-104">示例 Outlook Social Connector (OSC) 提供程序模板为您提供一个框架，用于实现 OSC 提供程序。</span><span class="sxs-lookup"><span data-stu-id="94459-104">The sample Outlook Social Connector (OSC) provider templates give you a framework for implementing an OSC provider.</span></span> <span data-ttu-id="94459-105">C + + C# 和 Visual Basic 中提供了提供程序模板。</span><span class="sxs-lookup"><span data-stu-id="94459-105">The provider templates are available in C++, C#, and Visual Basic.</span></span> <span data-ttu-id="94459-106">这些模板是只提供程序开发; 的起始点模板不能解决编写为提供程序的实现代码和创建提供程序的安装包。</span><span class="sxs-lookup"><span data-stu-id="94459-106">These templates are just a starting point for your provider development; the templates do not address writing the implementation code for the provider and creating a setup package for the provider.</span></span> <span data-ttu-id="94459-107">下面的过程演示如何在您开始开发提供程序时应用的 OSC 提供程序模板。</span><span class="sxs-lookup"><span data-stu-id="94459-107">The following procedure shows how to apply an OSC provider template when you begin to develop a provider.</span></span>
  
### <a name="to-apply-an-osc-provider-template"></a><span data-ttu-id="94459-108">若要应用的 OSC 提供程序模板</span><span class="sxs-lookup"><span data-stu-id="94459-108">To apply an OSC provider template</span></span>

1. <span data-ttu-id="94459-109">在**开始**菜单中，右键单击**Microsoft Visual Studio 2010** ，然后单击**以管理员身份运行**命令。</span><span class="sxs-lookup"><span data-stu-id="94459-109">On the **Start** menu, right-click **Microsoft Visual Studio 2010** and click the **Run as administrator** command.</span></span> <span data-ttu-id="94459-110">出现提示时，请单击**是**以管理员身份运行 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="94459-110">When prompted, click **Yes** to run Visual Studio as an administrator.</span></span> 
    
2. <span data-ttu-id="94459-111">将项目名称和模板中的命名空间更改为您的项目名称和命名空间标识符。</span><span class="sxs-lookup"><span data-stu-id="94459-111">Change the project name and namespace in the template to your project name and namespace identifiers.</span></span>
    
3. <span data-ttu-id="94459-112">修改**AssemblyInfo**类指定相应的程序集信息。</span><span class="sxs-lookup"><span data-stu-id="94459-112">Modify the **AssemblyInfo** class to specify the appropriate assembly information.</span></span> 
    
4. <span data-ttu-id="94459-113">实现接口成员标记为**待办事项**并根据需要添加更多的依赖关系和参考。</span><span class="sxs-lookup"><span data-stu-id="94459-113">Implement the interface members marked as **To-Do** and add more dependencies and references, as required.</span></span> 
    
5. <span data-ttu-id="94459-114">生成项目。</span><span class="sxs-lookup"><span data-stu-id="94459-114">Build the project.</span></span>
    
6. <span data-ttu-id="94459-115">确保提供程序程序集 ProgID 列为下的键`HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders`。</span><span class="sxs-lookup"><span data-stu-id="94459-115">Ensure that the provider assembly ProgID is listed as a key under  `HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders`.</span></span>
    
7. <span data-ttu-id="94459-116">分发安装项目，请在 Visual Studio 或您选择的安装程序工具创建安装项目。</span><span class="sxs-lookup"><span data-stu-id="94459-116">To distribute the setup project, create a setup project in Visual Studio or a setup tool of your choice.</span></span>
    
8. <span data-ttu-id="94459-117">安装项目应完成 COM 注册您的程序集，并还创建 ProgID 键，如步骤 5 中列出。</span><span class="sxs-lookup"><span data-stu-id="94459-117">Your setup project should complete COM registration for your assembly and also create the ProgID key as listed in step 5.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="94459-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94459-118">See also</span></span>

- [<span data-ttu-id="94459-119">下载示例</span><span class="sxs-lookup"><span data-stu-id="94459-119">Downloading the Samples</span></span>](downloading-the-samples.md)
- [<span data-ttu-id="94459-120">OSC 示例模板</span><span class="sxs-lookup"><span data-stu-id="94459-120">OSC Sample Templates</span></span>](osc-sample-templates.md)

