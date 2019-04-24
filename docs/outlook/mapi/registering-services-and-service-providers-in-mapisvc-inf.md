---
title: 在 mapisvc.inf 中注册服务和服务提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: a04acf17-4b2d-458e-9852-b6074acac096
description: '上次修改时间: 2013 年7月18日'
ms.openlocfilehash: adc6318ab36818b4c423bb6b1dc1b083b3fb54eb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328369"
---
# <a name="registering-services-and-service-providers-in-mapisvcinf"></a>在 mapisvc.inf 中注册服务和服务提供程序

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
若要在系统上安装新的提供程序, 则需要更新 mapisvc.inf 文件以指向新的提供程序。 配置过程中设置的标准属性, 其中包括以下内容: 通知 MAPI 查找提供程序的动态链接库 (.dll) 的位置:
  
- **PR_SERVICE_DLL_NAME**在 **[邮件服务]** 部分中指定。 
    
- **PR_PROVIDER_DLL_NAME**在 **[服务提供程序]** 部分中指定。 
    
> [!NOTE]
> 预期是设置提供程序的 .dll 的名称 (不带后缀 "32")。 然后, MAPI 将通过在路径上查找提供程序来加载提供程序。 
  
## <a name="putting-a-path-in-mapisvcinf"></a>在 mapisvc.inf 中放置路径

大多数应用程序都是在 "程序文件" 下安装的, 需要更新路径变量以允许 MAPI 提供程序正常工作。 通过一些限制, Microsoft Outlook 2010 和 Outlook 2013 可以容纳 MAPI 提供程序的完整路径。
  
在 mapisvc.inf 中注册提供程序时, 可以在 MAPI 属性**PR_SERVICE_DLL_NAME**和**PR_PROVIDER_DLL_NAME**中添加提供程序的完整路径。
  
在这两个属性中, 完整路径必须不带后缀 "32", 因为 MAPI 继续在查找文件之前将其追加到文件名。 这意味着, 如果注册路径 "c:\mypath\myprovider.dll", MAPI 将尝试加载 "c:\mypath\myprovider32.dll"。
  
由于 Outlook 的 MAPI 最初并不是为了容纳完整路径而设计的, 因此, 通过查找字符串中的第一个句点 (这意味着包含其他句点的路径不起作用) 来完成此插入 "32" 后缀, 因此不能使用类似路径, 如"c:\my.path\myprovider.dll" 或 "c:\mypath\my.provider.dll"。
  
有时, 在存储提供程序中, 您将使用**WrapStoreEntryID**函数生成条目标识符, 该函数接受提供程序的名称作为参数。 
  
> [!IMPORTANT]
> 如果在 mapisvc.inf 中使用了完整路径, 则必须在对**WrapStoreEntryID**的任何调用中使用相同的路径。 
  
此外, 您使用的路径可以使用[GetACP](https://msdn.microsoft.com/library/windows/desktop/dd318070%28v=vs.85%29.aspx/)函数提供的代码页在 Unicode 和 Unicode 之间进行转换。 
  
> [!CAUTION]
> 如果您选择的路径包含无法在[MultiByteToWideChar](https://msdn.microsoft.com/library/windows/desktop/dd319072%28v=vs.85%29.aspx/)和[WideCharToMultiByte](https://msdn.microsoft.com/library/windows/desktop/dd374130%28v=vs.85%29.aspx/)函数中使用的字符, 则会遇到故障。 
  
有关此功能的演示, 已修订 GitHub 上的[包装 PST 示例](https://github.com/stephenegriffin/Outlook2010CodeSamples)-相关功能位于**MergeWithMapiSvc**和**GenerateProviderPath**中。
  

