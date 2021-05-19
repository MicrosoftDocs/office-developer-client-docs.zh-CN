---
title: 创建表单配置文件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: aaf3b33d-ad2d-4ef8-847f-1ab1eaf08706
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 97ecafb2e4159c680fd23607f5ed6f8ea3156de7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425216"
---
# <a name="creating-a-form-configuration-file"></a><span data-ttu-id="44f7d-103">创建表单配置文件</span><span class="sxs-lookup"><span data-stu-id="44f7d-103">Creating a Form Configuration File</span></span>

  
  
<span data-ttu-id="44f7d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="44f7d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="44f7d-105">表单配置文件向使用的表单管理器和客户端应用程序提供有关表单的信息。</span><span class="sxs-lookup"><span data-stu-id="44f7d-105">A form configuration file provides information about a form both to the form manager being used and to client applications.</span></span> <span data-ttu-id="44f7d-106">表单配置文件包含表单的扩展规范，包括由表单发布的供邮件客户端使用的属性、由表单实现动词以及表单支持的平台。</span><span class="sxs-lookup"><span data-stu-id="44f7d-106">A form configuration file contains an extensive specification for a form, including the properties published by the form for use by messaging clients, the verbs implemented by the form, and the platforms supported by the form.</span></span>
  
<span data-ttu-id="44f7d-107">表单配置文件是扩展名为 .cfg 的文件，其格式类似于Windows文件。</span><span class="sxs-lookup"><span data-stu-id="44f7d-107">A form configuration file is a file with a .cfg extension, and has a format similar to a Windows initialization file.</span></span> <span data-ttu-id="44f7d-108">它是一个包含许多节的纯文本文件。</span><span class="sxs-lookup"><span data-stu-id="44f7d-108">It is a plain text file with a number of sections.</span></span> <span data-ttu-id="44f7d-109">每个节以节名称开头，括在方括号中。</span><span class="sxs-lookup"><span data-stu-id="44f7d-109">Each section begins with a section name, enclosed in square brackets.</span></span> <span data-ttu-id="44f7d-110">每个节包含一行或多行，用于定义与节相关的值和设置。</span><span class="sxs-lookup"><span data-stu-id="44f7d-110">Each section contains one or more lines that define values and settings relevant to that section.</span></span> <span data-ttu-id="44f7d-111">值具有以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="44f7d-111">Values have one of the following types:</span></span>
  
- <span data-ttu-id="44f7d-112">String</span><span class="sxs-lookup"><span data-stu-id="44f7d-112">String</span></span>
    
- <span data-ttu-id="44f7d-113">显示的字符串</span><span class="sxs-lookup"><span data-stu-id="44f7d-113">Displayed string</span></span>
    
- <span data-ttu-id="44f7d-114">平台字符串</span><span class="sxs-lookup"><span data-stu-id="44f7d-114">Platform string</span></span>
    
- <span data-ttu-id="44f7d-115">路径名称</span><span class="sxs-lookup"><span data-stu-id="44f7d-115">Path name</span></span>
    
- <span data-ttu-id="44f7d-116">整数</span><span class="sxs-lookup"><span data-stu-id="44f7d-116">Integer</span></span>
    
- <span data-ttu-id="44f7d-117">GUID</span><span class="sxs-lookup"><span data-stu-id="44f7d-117">GUID</span></span>
    
<span data-ttu-id="44f7d-118">有关 .cfg 文件的各个部分的信息，请参阅 File [Format of Form Configuration Files](file-format-of-form-configuration-files.md)。</span><span class="sxs-lookup"><span data-stu-id="44f7d-118">For more information about the sections of a .cfg file, see [File Format of Form Configuration Files](file-format-of-form-configuration-files.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="44f7d-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="44f7d-119">See also</span></span>



[<span data-ttu-id="44f7d-120">开发 MAPI 表单服务器</span><span class="sxs-lookup"><span data-stu-id="44f7d-120">Developing MAPI Form Servers</span></span>](developing-mapi-form-servers.md)

