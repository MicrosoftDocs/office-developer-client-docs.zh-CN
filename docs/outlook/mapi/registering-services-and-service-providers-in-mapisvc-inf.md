---
title: 注册 MapiSvc.inf 中的服务和服务提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: a04acf17-4b2d-458e-9852-b6074acac096
description: 上次修改时间： 2013 年 7 月 18 日
ms.openlocfilehash: c74257b84636952b26c5a624f4f7f76f66be9149
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566920"
---
# <a name="registering-services-and-service-providers-in-mapisvcinf"></a>注册 MapiSvc.inf 中的服务和服务提供程序

 
  
**适用于**： Outlook 2013 |Outlook 2016 
  
系统上安装新的提供程序需要更新 MapiSvc.inf 文件以指向新的提供程序。 标准属性设置在配置期间，其中包括以下，告知 MAPI 在哪里可以找到提供程序的动态链接库 (.dll):
  
- 在 **[消息服务]** 部分中指定**PR_SERVICE_DLL_NAME** 。 
    
- **PR_PROVIDER_DLL_NAME** **[服务提供商]** 节中指定。 
    
> [!NOTE]
> 预期结果是.dll 的您设置提供程序 （而不使用后缀"32"） 的名称。 MAPI 然后通过路径上查找加载您的提供商。 
  
## <a name="putting-a-path-in-mapisvcinf"></a>将路径放在 MapiSvc.inf

大多数应用程序安装在 Program Files，需要更新到 path 变量以允许 MAPI 提供程序工作下。 一些限制与 Microsoft Outlook 2010 和 Outlook 2013 可以适应到 MAPI 提供程序的完整路径。
  
时在 MapiSvc.inf 注册提供程序，您无法 MAPI 属性**PR_SERVICE_DLL_NAME**和**PR_PROVIDER_DLL_NAME**中提供程序将的完整路径。
  
在这两个属性的完整路径必须是不带后缀"32"中，因为 MAPI 继续追加到文件名查找您的文件之前。 这意味着，如果您注册"c:\mypath\myprovider.dll"的路径，MAPI 将尝试加载"c:\mypath\myprovider32.dll"。
  
由于 Outlook 的 MAPI 未最初设计以适应完整路径，它通过查看在字符串中，这意味着，包含其他句点的路径不能工作，因此您不能使用路径，如的第一段完成的"32"后缀此插入"c:\my.path\myprovider.dll"或者"c:\mypath\my.provider.dll"。
  
有时的存储提供程序中将生成使用**WrapStoreEntryID**函数，它提供程序名称作为参数采用项标识符。 
  
> [!IMPORTANT]
> 如果您在 MapiSvc.inf 中使用完整路径，您必须**WrapStoreEntryID**调用中使用同一个路径。 
  
此外，可能会与 Unicode 使用供稿[GetACP](http://msdn.microsoft.com/en-us/library/windows/desktop/dd318070%28v=vs.85%29.aspx/)函数的代码页转换您使用的路径。 
  
> [!CAUTION]
> 如果您选择包含不能排除通过[MultiByteToWideChar](http://msdn.microsoft.com/en-us/library/windows/desktop/dd319072%28v=vs.85%29.aspx/)和[WideCharToMultiByte](http://msdn.microsoft.com/en-us/library/windows/desktop/dd374130%28v=vs.85%29.aspx/)函数此类的往返行程的字符的路径，则会出现故障。 
  
此功能的演示，CodePlex 上的[自动换行 PST 示例](http://ol2010mapisamples.codeplex.com/)已经过修改-相关的功能是**MergeWithMapiSvc**和**GenerateProviderPath**中。
  

