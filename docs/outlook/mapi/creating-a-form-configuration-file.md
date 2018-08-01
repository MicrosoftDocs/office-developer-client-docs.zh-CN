---
title: 创建表单配置文件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: aaf3b33d-ad2d-4ef8-847f-1ab1eaf08706
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 9ceb7ad347e73f69eca3463ed2edc4438a45a21f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774729"
---
# <a name="creating-a-form-configuration-file"></a><span data-ttu-id="67e7b-103">创建表单配置文件</span><span class="sxs-lookup"><span data-stu-id="67e7b-103">Creating a Form Configuration File</span></span>

  
  
<span data-ttu-id="67e7b-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="67e7b-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="67e7b-105">窗体配置文件正在使用的窗体管理器和客户端应用程序提供有关表单的信息。</span><span class="sxs-lookup"><span data-stu-id="67e7b-105">A form configuration file provides information about a form both to the form manager being used and to client applications.</span></span> <span data-ttu-id="67e7b-106">窗体配置文件包含大量的窗体，包括用于表单发布的消息客户端、 窗体中，通过实现的动作和按窗体所支持的平台的属性规范。</span><span class="sxs-lookup"><span data-stu-id="67e7b-106">A form configuration file contains an extensive specification for a form, including the properties published by the form for use by messaging clients, the verbs implemented by the form, and the platforms supported by the form.</span></span>
  
<span data-ttu-id="67e7b-107">窗体配置文件是一个文件扩展名为.cfg 具有类似于 Windows 的初始化文件的格式。</span><span class="sxs-lookup"><span data-stu-id="67e7b-107">A form configuration file is a file with a .cfg extension, and has a format similar to a Windows initialization file.</span></span> <span data-ttu-id="67e7b-108">它是纯文本文件的节的编号。</span><span class="sxs-lookup"><span data-stu-id="67e7b-108">It is a plain text file with a number of sections.</span></span> <span data-ttu-id="67e7b-109">每一节开始部分名称，用方括号括起来。</span><span class="sxs-lookup"><span data-stu-id="67e7b-109">Each section begins with a section name, enclosed in square brackets.</span></span> <span data-ttu-id="67e7b-110">每个部分包含定义值和与该节相关的设置的一个或多个行。</span><span class="sxs-lookup"><span data-stu-id="67e7b-110">Each section contains one or more lines that define values and settings relevant to that section.</span></span> <span data-ttu-id="67e7b-111">值具有以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="67e7b-111">Values have one of the following types:</span></span>
  
- <span data-ttu-id="67e7b-112">字符串</span><span class="sxs-lookup"><span data-stu-id="67e7b-112">String</span></span>
    
- <span data-ttu-id="67e7b-113">显示的字符串</span><span class="sxs-lookup"><span data-stu-id="67e7b-113">Displayed string</span></span>
    
- <span data-ttu-id="67e7b-114">平台字符串</span><span class="sxs-lookup"><span data-stu-id="67e7b-114">Platform string</span></span>
    
- <span data-ttu-id="67e7b-115">路径名称</span><span class="sxs-lookup"><span data-stu-id="67e7b-115">Path name</span></span>
    
- <span data-ttu-id="67e7b-116">整数</span><span class="sxs-lookup"><span data-stu-id="67e7b-116">Integer</span></span>
    
- <span data-ttu-id="67e7b-117">GUID</span><span class="sxs-lookup"><span data-stu-id="67e7b-117">GUID</span></span>
    
<span data-ttu-id="67e7b-118">有关.cfg 文件的部分的详细信息，请参阅[窗体配置文件的文件格式](file-format-of-form-configuration-files.md)。</span><span class="sxs-lookup"><span data-stu-id="67e7b-118">For more information about the sections of a .cfg file, see [File Format of Form Configuration Files](file-format-of-form-configuration-files.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="67e7b-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="67e7b-119">See also</span></span>



[<span data-ttu-id="67e7b-120">开发 MAPI 表单服务器</span><span class="sxs-lookup"><span data-stu-id="67e7b-120">Developing MAPI Form Servers</span></span>](developing-mapi-form-servers.md)

