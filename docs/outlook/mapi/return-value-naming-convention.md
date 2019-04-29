---
title: 返回值命名约定
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2c1cdd7b-82f1-46f2-a7ce-e0efe857b7cd
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6786e1ca901215abd709a11401c3026d62c6ffc8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423613"
---
# <a name="return-value-naming-convention"></a><span data-ttu-id="b678e-103">返回值命名约定</span><span class="sxs-lookup"><span data-stu-id="b678e-103">Return Value Naming Convention</span></span>

  
  
<span data-ttu-id="b678e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b678e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b678e-105">MAPICODE。H 头文件包含客户端或服务提供程序可能从接口方法实现中返回的很多值, 或者可能看到从调用返回的一些值。</span><span class="sxs-lookup"><span data-stu-id="b678e-105">The MAPICODE.H header file contains many of the values that a client or service provider might return from an interface method implementation or might see returned from a call.</span></span>
  
<span data-ttu-id="b678e-106">代表警告和失败条件的代码遵循以前缀 MAPI、下划线和 W 或 E 开头的不同命名约定, 以指示代码的类型。</span><span class="sxs-lookup"><span data-stu-id="b678e-106">The codes to represent warning and failure conditions follow a different naming convention that begins with the prefix MAPI, an underscore, and either a W or an E to indicate the type of code.</span></span> <span data-ttu-id="b678e-107">代码的其余部分是用于描述条件的短字符字符串。</span><span class="sxs-lookup"><span data-stu-id="b678e-107">The rest of the code is a short character string to describe the condition.</span></span> <span data-ttu-id="b678e-108">字符串中的每个单词都用下划线分隔。</span><span class="sxs-lookup"><span data-stu-id="b678e-108">Each word in the string is separated by an underscore.</span></span> <span data-ttu-id="b678e-109">例如, 错误值 MAPI_E_TOO_COMPLEX 指示实现无法处理在调用中请求的任何内容。</span><span class="sxs-lookup"><span data-stu-id="b678e-109">For example, the error value MAPI_E_TOO_COMPLEX indicates that the implementation could not handle whatever was being requested in the call.</span></span> <span data-ttu-id="b678e-110">警告值 MAPI_W_PARTIAL_COMPLETION 指示调用成功, 但出现问题。</span><span class="sxs-lookup"><span data-stu-id="b678e-110">The warning value MAPI_W_PARTIAL_COMPLETION indicates that the call succeeded, but that there were problems.</span></span> <span data-ttu-id="b678e-111">仅成功完成部分操作。</span><span class="sxs-lookup"><span data-stu-id="b678e-111">Only part of the operation was completed successfully.</span></span>
  

