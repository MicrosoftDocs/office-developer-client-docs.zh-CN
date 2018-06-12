---
title: MAPI 表单对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: eb9107d9-ad5c-4264-a457-dea193597dc9
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 426d3d5787f4ef8cde2883c5e2eb3699dd664965
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776242"
---
# <a name="mapi-form-objects"></a><span data-ttu-id="e0023-103">MAPI 表单对象</span><span class="sxs-lookup"><span data-stu-id="e0023-103">MAPI Form Objects</span></span>

  
  
<span data-ttu-id="e0023-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e0023-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e0023-105">若要显示特定消息并允许用户与之交互的窗体服务器动态创建窗体对象。</span><span class="sxs-lookup"><span data-stu-id="e0023-105">Form objects are created dynamically by form servers in order to display specific messages and allow users to interact with them.</span></span> <span data-ttu-id="e0023-106">因此，form 对象是类的从[IMAPIForm](imapiformiunknown.md)由表单服务器实现派生的实例。</span><span class="sxs-lookup"><span data-stu-id="e0023-106">A form object is, therefore, an instantiation of the class derived from [IMAPIForm](imapiformiunknown.md) that is implemented by the form server.</span></span> <span data-ttu-id="e0023-107">当客户端应用程序打开邮件时，该邮件类的窗体服务器创建窗体对象来处理邮件。</span><span class="sxs-lookup"><span data-stu-id="e0023-107">When a client application opens a message, the form server for that message class creates a form object to handle the message.</span></span> <span data-ttu-id="e0023-108">Form 对象然后创建其界面，并在其中显示消息的属性。</span><span class="sxs-lookup"><span data-stu-id="e0023-108">The form object then creates its interface and displays the properties of the message in it.</span></span> <span data-ttu-id="e0023-109">Form 对象和其界面将一直保持到用户将其关闭。</span><span class="sxs-lookup"><span data-stu-id="e0023-109">The form object and its interface persists until the user closes it.</span></span> <span data-ttu-id="e0023-110">Form 对象处理邮件的属性的值对的任何更改。</span><span class="sxs-lookup"><span data-stu-id="e0023-110">The form object handles any changes to the values of the message's properties.</span></span> 
  
<span data-ttu-id="e0023-111">此外，MAPI 表单接口定义一种机制所加载和显示的消息的一系列一个 form 对象。</span><span class="sxs-lookup"><span data-stu-id="e0023-111">Additionally, the MAPI form interfaces define a mechanism by which one form object can load and display a series of messages.</span></span> <span data-ttu-id="e0023-112">这是效率机制，因为它避免不必要的销毁和创建的消息对象和其接口。</span><span class="sxs-lookup"><span data-stu-id="e0023-112">This is an efficiency mechanism, as it avoids needless destruction and creation of message objects and their interfaces.</span></span> <span data-ttu-id="e0023-113">时请求的消息的客户端加载其他消息，form 对象应将任何更改保存到当前消息的属性。</span><span class="sxs-lookup"><span data-stu-id="e0023-113">When requested by the messaging client to load a different message, the form object should save any changes to the current message's properties.</span></span>
  
<span data-ttu-id="e0023-114">有关客户端应用程序的角度来看表单对象的信息，请参阅[MAPI 自定义窗体对象](mapi-custom-form-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="e0023-114">For information on a client application's perspective of form objects, see [MAPI Custom Form Objects](mapi-custom-form-objects.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e0023-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0023-115">See also</span></span>



[<span data-ttu-id="e0023-116">MAPI 表单</span><span class="sxs-lookup"><span data-stu-id="e0023-116">MAPI Forms</span></span>](mapi-forms.md)

