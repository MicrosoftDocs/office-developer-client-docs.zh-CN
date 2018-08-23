---
title: MAPI 表单接口
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 611213c9-e758-4366-b193-fc62181d3d1f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f37d398167e8210a2fd67ff08e63572eb6c9db9c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585722"
---
# <a name="mapi-form-interfaces"></a><span data-ttu-id="26ad2-103">MAPI 表单接口</span><span class="sxs-lookup"><span data-stu-id="26ad2-103">MAPI Form Interfaces</span></span>

  
  
<span data-ttu-id="26ad2-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="26ad2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="26ad2-105">MAPI 定义以下与表单相关的接口。</span><span class="sxs-lookup"><span data-stu-id="26ad2-105">MAPI defines the following interfaces relating to forms.</span></span>
  
|<span data-ttu-id="26ad2-106">**接口名称**</span><span class="sxs-lookup"><span data-stu-id="26ad2-106">**Interface name**</span></span>|<span data-ttu-id="26ad2-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="26ad2-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="26ad2-108">IMAPIForm</span><span class="sxs-lookup"><span data-stu-id="26ad2-108">IMAPIForm</span></span>](imapiformiunknown.md) <br/> |<span data-ttu-id="26ad2-109">处理表单对象并处理窗体对象命令。</span><span class="sxs-lookup"><span data-stu-id="26ad2-109">Manipulates form objects and handles form object commands.</span></span>  <br/> |
|[<span data-ttu-id="26ad2-110">IMAPIFormAdviseSink</span><span class="sxs-lookup"><span data-stu-id="26ad2-110">IMAPIFormAdviseSink</span></span>](imapiformadvisesinkiunknown.md) <br/> |<span data-ttu-id="26ad2-111">确定是否 form 对象可以处理下一条消息，并更改 form 对象的一个或下一个状态。</span><span class="sxs-lookup"><span data-stu-id="26ad2-111">Determines if the form object can handle the next message and changes the next or previous state of the form object.</span></span>  <br/> |
|[<span data-ttu-id="26ad2-112">IMAPIFormContainer</span><span class="sxs-lookup"><span data-stu-id="26ad2-112">IMAPIFormContainer</span></span>](imapiformcontaineriunknown.md) <br/> |<span data-ttu-id="26ad2-113">安装、 卸载和针对特定窗体容器的窗体服务器的解析支持。</span><span class="sxs-lookup"><span data-stu-id="26ad2-113">Supports installation, deinstallation, and resolution of form servers against a specific form container.</span></span>  <br/> |
|[<span data-ttu-id="26ad2-114">IMAPIFormFactory</span><span class="sxs-lookup"><span data-stu-id="26ad2-114">IMAPIFormFactory</span></span>](imapiformfactoryiunknown.md) <br/> |<span data-ttu-id="26ad2-115">支持使用可配置的运行时窗体服务器。</span><span class="sxs-lookup"><span data-stu-id="26ad2-115">Supports the use of configurable run-time form servers.</span></span>  <br/> |
|[<span data-ttu-id="26ad2-116">IMAPIFormInfo</span><span class="sxs-lookup"><span data-stu-id="26ad2-116">IMAPIFormInfo</span></span>](imapiforminfoimapiprop.md) <br/> |<span data-ttu-id="26ad2-117">允许客户端应用程序使用的特定于邮件类的属性。</span><span class="sxs-lookup"><span data-stu-id="26ad2-117">Enables client applications to work with properties that are specific to a message class.</span></span>  <br/> |
|[<span data-ttu-id="26ad2-118">IMAPIFormMgr</span><span class="sxs-lookup"><span data-stu-id="26ad2-118">IMAPIFormMgr</span></span>](imapiformmgriunknown.md) <br/> |<span data-ttu-id="26ad2-119">启用客户端应用程序，以获取有关窗体服务器的信息、 激活窗体服务器，并将窗体服务器安装在邮件系统中。</span><span class="sxs-lookup"><span data-stu-id="26ad2-119">Enables client applications to get information about form servers, activates form servers, and installs form servers in the messaging system.</span></span>  <br/> |
|[<span data-ttu-id="26ad2-120">IMAPIMessageSite</span><span class="sxs-lookup"><span data-stu-id="26ad2-120">IMAPIMessageSite</span></span>](imapimessagesiteiunknown.md) <br/> |<span data-ttu-id="26ad2-121">用来处理表单对象相关联的邮件。</span><span class="sxs-lookup"><span data-stu-id="26ad2-121">Used to manipulate messages associated with form objects.</span></span>  <br/> |
|[<span data-ttu-id="26ad2-122">IMAPIViewAdviseSink</span><span class="sxs-lookup"><span data-stu-id="26ad2-122">IMAPIViewAdviseSink</span></span>](imapiviewadvisesinkiunknown.md) <br/> |<span data-ttu-id="26ad2-123">通知事件发生在窗体对象中的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="26ad2-123">Notifies client applications that an event has occurred in the form object.</span></span>  <br/> |
|[<span data-ttu-id="26ad2-124">IMAPIViewContext</span><span class="sxs-lookup"><span data-stu-id="26ad2-124">IMAPIViewContext</span></span>](imapiviewcontextiunknown.md) <br/> |<span data-ttu-id="26ad2-125">用于响应窗体对象中的下一步、 上一步，和删除命令。</span><span class="sxs-lookup"><span data-stu-id="26ad2-125">Used to respond to Next, Previous, and Delete commands in the form object.</span></span>  <br/> |
|[<span data-ttu-id="26ad2-126">IPersistMessage</span><span class="sxs-lookup"><span data-stu-id="26ad2-126">IPersistMessage</span></span>](ipersistmessageiunknown.md) <br/> |<span data-ttu-id="26ad2-127">用于保存、 初始化和加载窗体与邮件存储的对象。</span><span class="sxs-lookup"><span data-stu-id="26ad2-127">Used to save, initialize, and load form objects to and from message storage.</span></span>  <br/> |
   
<span data-ttu-id="26ad2-128">MAPI 表单接口的方法的详细信息，请参阅这些接口的文档。</span><span class="sxs-lookup"><span data-stu-id="26ad2-128">For more information about the methods of the MAPI form interfaces, see the documentation for these interfaces.</span></span> <span data-ttu-id="26ad2-129">您不必实现的所有 MAPI 表单接口以创建自定义窗体。</span><span class="sxs-lookup"><span data-stu-id="26ad2-129">You do not have to implement all of the MAPI form interfaces in order to create a custom form.</span></span> <span data-ttu-id="26ad2-130">窗体本身，只需实现**IPersistMessage**， **IMAPIForm**，以及**IMAPIFormAdviseSink**接口。</span><span class="sxs-lookup"><span data-stu-id="26ad2-130">A form itself requires only that you implement the **IPersistMessage**, **IMAPIForm**, and **IMAPIFormAdviseSink** interfaces.</span></span> <span data-ttu-id="26ad2-131">此外，它也是最好**IMAPIFormFactory**和**IMAPIFormInfo**实现。</span><span class="sxs-lookup"><span data-stu-id="26ad2-131">Additionally, it is also a good idea to implement **IMAPIFormFactory** and **IMAPIFormInfo**.</span></span> <span data-ttu-id="26ad2-132">用于 OLE 法规遵从性， **IMAPIFormFactory**并**IMAPIFormInfo**使编写完善的客户端应用程序能够更好地利用窗体。</span><span class="sxs-lookup"><span data-stu-id="26ad2-132">**IMAPIFormFactory** is useful for OLE compliance, and **IMAPIFormInfo** enables well-written client applications to make better use of your forms.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="26ad2-133">严格来说， **IMAPIFormAdviseSink**是一个可选的接口。</span><span class="sxs-lookup"><span data-stu-id="26ad2-133">Strictly speaking, **IMAPIFormAdviseSink** is an optional interface.</span></span> <span data-ttu-id="26ad2-134">但是，强烈建议在窗体服务器中实现。</span><span class="sxs-lookup"><span data-stu-id="26ad2-134">However, it is strongly recommended that you implement it in your form servers.</span></span> <span data-ttu-id="26ad2-135">该接口是非常重要的消息客户端和窗体服务器之间的有效交互尤其是当您的窗体服务器的多个邮件邮件类是所涉及的。</span><span class="sxs-lookup"><span data-stu-id="26ad2-135">This interface is critical to efficient interaction between messaging clients and form servers, especially when several messages of your form server's message class are being dealt with.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="26ad2-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="26ad2-136">See also</span></span>



[<span data-ttu-id="26ad2-137">MAPI 表单</span><span class="sxs-lookup"><span data-stu-id="26ad2-137">MAPI Forms</span></span>](mapi-forms.md)

