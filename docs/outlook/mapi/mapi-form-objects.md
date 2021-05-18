---
title: MAPI 窗体对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: eb9107d9-ad5c-4264-a457-dea193597dc9
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 5a7c6c575f277a91a18f0d834e26d3d376613fba
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404783"
---
# <a name="mapi-form-objects"></a><span data-ttu-id="1f6be-103">MAPI 窗体对象</span><span class="sxs-lookup"><span data-stu-id="1f6be-103">MAPI Form Objects</span></span>

  
  
<span data-ttu-id="1f6be-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1f6be-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1f6be-105">表单对象由表单服务器动态创建，以便显示特定消息并允许用户与其交互。</span><span class="sxs-lookup"><span data-stu-id="1f6be-105">Form objects are created dynamically by form servers in order to display specific messages and allow users to interact with them.</span></span> <span data-ttu-id="1f6be-106">因此，表单对象是由表单服务器实现的 [IMAPIForm](imapiformiunknown.md) 派生的类实例化。</span><span class="sxs-lookup"><span data-stu-id="1f6be-106">A form object is, therefore, an instantiation of the class derived from [IMAPIForm](imapiformiunknown.md) that is implemented by the form server.</span></span> <span data-ttu-id="1f6be-107">当客户端应用程序打开邮件时，该邮件类的窗体服务器会创建一个表单对象来处理邮件。</span><span class="sxs-lookup"><span data-stu-id="1f6be-107">When a client application opens a message, the form server for that message class creates a form object to handle the message.</span></span> <span data-ttu-id="1f6be-108">然后，表单对象创建其接口，并显示其中的消息属性。</span><span class="sxs-lookup"><span data-stu-id="1f6be-108">The form object then creates its interface and displays the properties of the message in it.</span></span> <span data-ttu-id="1f6be-109">窗体对象及其接口将一直保留，直到用户关闭它。</span><span class="sxs-lookup"><span data-stu-id="1f6be-109">The form object and its interface persists until the user closes it.</span></span> <span data-ttu-id="1f6be-110">form 对象处理对邮件属性值的任何更改。</span><span class="sxs-lookup"><span data-stu-id="1f6be-110">The form object handles any changes to the values of the message's properties.</span></span> 
  
<span data-ttu-id="1f6be-111">此外，MAPI 表单接口还定义了一种机制，一个表单对象可以通过该机制加载和显示一系列消息。</span><span class="sxs-lookup"><span data-stu-id="1f6be-111">Additionally, the MAPI form interfaces define a mechanism by which one form object can load and display a series of messages.</span></span> <span data-ttu-id="1f6be-112">这是一种效率机制，因为它可以避免不必要的破坏和创建邮件对象及其接口。</span><span class="sxs-lookup"><span data-stu-id="1f6be-112">This is an efficiency mechanism, as it avoids needless destruction and creation of message objects and their interfaces.</span></span> <span data-ttu-id="1f6be-113">当邮件客户端请求加载其他邮件时，表单对象应保存对当前邮件属性的任何更改。</span><span class="sxs-lookup"><span data-stu-id="1f6be-113">When requested by the messaging client to load a different message, the form object should save any changes to the current message's properties.</span></span>
  
<span data-ttu-id="1f6be-114">有关客户端应用程序对表单对象的角度的信息，请参阅[MAPI Custom Form Objects。](mapi-custom-form-objects.md)</span><span class="sxs-lookup"><span data-stu-id="1f6be-114">For information on a client application's perspective of form objects, see [MAPI Custom Form Objects](mapi-custom-form-objects.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1f6be-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f6be-115">See also</span></span>



[<span data-ttu-id="1f6be-116">MAPI 表单</span><span class="sxs-lookup"><span data-stu-id="1f6be-116">MAPI Forms</span></span>](mapi-forms.md)

