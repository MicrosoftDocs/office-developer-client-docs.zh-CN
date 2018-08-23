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
ms.openlocfilehash: 0cece598d4ad337e29edb3bb98b302de900e056d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22593464"
---
# <a name="mapi-form-objects"></a><span data-ttu-id="56112-103">MAPI 表单对象</span><span class="sxs-lookup"><span data-stu-id="56112-103">MAPI Form Objects</span></span>

  
  
<span data-ttu-id="56112-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="56112-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="56112-105">若要显示特定消息并允许用户与之交互的窗体服务器动态创建窗体对象。</span><span class="sxs-lookup"><span data-stu-id="56112-105">Form objects are created dynamically by form servers in order to display specific messages and allow users to interact with them.</span></span> <span data-ttu-id="56112-106">因此，form 对象是类的从[IMAPIForm](imapiformiunknown.md)由表单服务器实现派生的实例。</span><span class="sxs-lookup"><span data-stu-id="56112-106">A form object is, therefore, an instantiation of the class derived from [IMAPIForm](imapiformiunknown.md) that is implemented by the form server.</span></span> <span data-ttu-id="56112-107">当客户端应用程序打开邮件时，该邮件类的窗体服务器创建窗体对象来处理邮件。</span><span class="sxs-lookup"><span data-stu-id="56112-107">When a client application opens a message, the form server for that message class creates a form object to handle the message.</span></span> <span data-ttu-id="56112-108">Form 对象然后创建其界面，并在其中显示消息的属性。</span><span class="sxs-lookup"><span data-stu-id="56112-108">The form object then creates its interface and displays the properties of the message in it.</span></span> <span data-ttu-id="56112-109">Form 对象和其界面将一直保持到用户将其关闭。</span><span class="sxs-lookup"><span data-stu-id="56112-109">The form object and its interface persists until the user closes it.</span></span> <span data-ttu-id="56112-110">Form 对象处理邮件的属性的值对的任何更改。</span><span class="sxs-lookup"><span data-stu-id="56112-110">The form object handles any changes to the values of the message's properties.</span></span> 
  
<span data-ttu-id="56112-111">此外，MAPI 表单接口定义一种机制所加载和显示的消息的一系列一个 form 对象。</span><span class="sxs-lookup"><span data-stu-id="56112-111">Additionally, the MAPI form interfaces define a mechanism by which one form object can load and display a series of messages.</span></span> <span data-ttu-id="56112-112">这是效率机制，因为它避免不必要的销毁和创建的消息对象和其接口。</span><span class="sxs-lookup"><span data-stu-id="56112-112">This is an efficiency mechanism, as it avoids needless destruction and creation of message objects and their interfaces.</span></span> <span data-ttu-id="56112-113">时请求的消息的客户端加载其他消息，form 对象应将任何更改保存到当前消息的属性。</span><span class="sxs-lookup"><span data-stu-id="56112-113">When requested by the messaging client to load a different message, the form object should save any changes to the current message's properties.</span></span>
  
<span data-ttu-id="56112-114">有关客户端应用程序的角度来看表单对象的信息，请参阅[MAPI 自定义窗体对象](mapi-custom-form-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="56112-114">For information on a client application's perspective of form objects, see [MAPI Custom Form Objects](mapi-custom-form-objects.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="56112-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56112-115">See also</span></span>



[<span data-ttu-id="56112-116">MAPI 表单</span><span class="sxs-lookup"><span data-stu-id="56112-116">MAPI Forms</span></span>](mapi-forms.md)

