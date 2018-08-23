---
title: 在此版本中弃用的 API 元素
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d0a6d182-961c-4496-a3bd-f643612527a5
description: 上次修改时间： 2012 年 6 月 25 日
ms.openlocfilehash: e40bcbfffc6f149837f4a11351f2bdbbf0dcc524
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571596"
---
# <a name="api-elements-deprecated-in-this-edition"></a><span data-ttu-id="4a9f0-103">在此版本中弃用的 API 元素</span><span class="sxs-lookup"><span data-stu-id="4a9f0-103">API Elements Deprecated in This Edition</span></span>

  
  
<span data-ttu-id="4a9f0-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4a9f0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4a9f0-105">Microsoft Outlook 2013 中弃用以下 API 元素。</span><span class="sxs-lookup"><span data-stu-id="4a9f0-105">The following API elements are deprecated in Microsoft Outlook 2013.</span></span> <span data-ttu-id="4a9f0-106">不再受支持和不应新项目中使用它们。</span><span class="sxs-lookup"><span data-stu-id="4a9f0-106">They are no longer supported and you should not use them in new projects.</span></span>
  
## <a name="deprecation-of-message-and-recipient-options"></a><span data-ttu-id="4a9f0-107">Deprecation 邮件和收件人选项</span><span class="sxs-lookup"><span data-stu-id="4a9f0-107">Deprecation of Message and Recipient Options</span></span>

<span data-ttu-id="4a9f0-108">以下 API 元素已弃用此版本中，因为已过时邮件和收件人的选项：</span><span class="sxs-lookup"><span data-stu-id="4a9f0-108">The following API elements are deprecated in this release because of obsolete message and recipient options:</span></span>
  
- <span data-ttu-id="4a9f0-109">**IXPLogon::RegisterOptions**— MAPI 子系统不能再调用此方法来建立传输提供程序的邮件和收件人选项的任何默认值。</span><span class="sxs-lookup"><span data-stu-id="4a9f0-109">**IXPLogon::RegisterOptions**—The MAPI subsystem no longer calls this method to establish any default values for message and recipient options for a transport provider.</span></span>
    
- <span data-ttu-id="4a9f0-110">**OPTIONDATA**— 此支持邮件和收件人选项属性的数据结构已过时。</span><span class="sxs-lookup"><span data-stu-id="4a9f0-110">**OPTIONDATA**—This data structure that supported properties for message and recipient options is obsolete.</span></span> <span data-ttu-id="4a9f0-111">MAPI 子系统不能再调用**IXPLogon::RegisterOptions**获取的任何消息或传输提供程序支持的特定地址类型的收件人选项。</span><span class="sxs-lookup"><span data-stu-id="4a9f0-111">The MAPI subsystem no longer calls **IXPLogon::RegisterOptions** to obtain any message or recipient options that a transport provider supports for a particular address type.</span></span> 
    
- <span data-ttu-id="4a9f0-112">**OPTIONCALLBACK**-此函数原型，其传输提供程序用于反过来，声明的回调函数和，用于解析提供程序的属性的 MAPI 子系统已过时。</span><span class="sxs-lookup"><span data-stu-id="4a9f0-112">**OPTIONCALLBACK**—This function prototype, which a transport provider used to declare a callback function and which, in turn, the MAPI subsystem used to resolve the provider's properties, is obsolete.</span></span> <span data-ttu-id="4a9f0-113">MAPI 子系统不能再调用**IXPLogon::RegisterOptions**或使用由传输提供程序返回任何回调函数。</span><span class="sxs-lookup"><span data-stu-id="4a9f0-113">The MAPI subsystem no longer calls **IXPLogon::RegisterOptions** or uses any callback function returned by the transport provider.</span></span> 
    
- <span data-ttu-id="4a9f0-114">**IMAPISession::MessageOptions**— MAPI 客户端与服务提供程序应不再调用此方法来显示属性，或允许用户设置控制特定的邮件和地址类型的属性。</span><span class="sxs-lookup"><span data-stu-id="4a9f0-114">**IMAPISession::MessageOptions**—MAPI client and service providers should no longer call this method to display properties or let users set properties that control a particular message and address type.</span></span> <span data-ttu-id="4a9f0-115">该方法将始终返回 MAPI_E_NOT_FOUND，这表明没有为特定邮件的邮件选项。</span><span class="sxs-lookup"><span data-stu-id="4a9f0-115">The method always returns MAPI_E_NOT_FOUND, which indicates that there are no message options for the particular message.</span></span>
    
- <span data-ttu-id="4a9f0-116">**IMAPISession::QueryDefaultMessageOpt**— MAPI 客户端与服务提供程序应不再调用此方法来检索控制消息选项的特定地址类型的属性。</span><span class="sxs-lookup"><span data-stu-id="4a9f0-116">**IMAPISession::QueryDefaultMessageOpt**—MAPI client and service providers should no longer call this method to retrieve properties that control message options for a particular address type.</span></span> <span data-ttu-id="4a9f0-117">方法无法再到任何属性值的数组返回一个指针。</span><span class="sxs-lookup"><span data-stu-id="4a9f0-117">The method no longer returns a pointer to any array of property values.</span></span>
    
- <span data-ttu-id="4a9f0-118">**IAddrBook::RecipOptions**— MAPI 客户端与服务提供程序应不再调用此方法来显示属性，或允许用户设置该控件处理的特定地址类型的收件人的属性。</span><span class="sxs-lookup"><span data-stu-id="4a9f0-118">**IAddrBook::RecipOptions**—MAPI client and service providers should no longer call this method to display properties or let users set properties that control processing for a recipient of a particular address type.</span></span> <span data-ttu-id="4a9f0-119">该方法将始终返回 MAPI_W_ERRORS_RETURNED，这表明没有特定收件人的收件人的选项。</span><span class="sxs-lookup"><span data-stu-id="4a9f0-119">The method always returns MAPI_W_ERRORS_RETURNED, which indicates that there are no recipient options for the particular recipient.</span></span>
    
- <span data-ttu-id="4a9f0-120">**IAddrBook::QueryDefaultRecipOpt**— MAPI 客户端与服务提供程序应不再调用此方法来检索控制收件人选项的特定地址类型的属性。</span><span class="sxs-lookup"><span data-stu-id="4a9f0-120">**IAddrBook::QueryDefaultRecipOpt**—MAPI client and service providers should no longer call this method to retrieve properties that control recipient options for a particular address type.</span></span> <span data-ttu-id="4a9f0-121">方法无法再到任何属性值的数组返回一个指针。</span><span class="sxs-lookup"><span data-stu-id="4a9f0-121">The method no longer returns a pointer to any array of property values.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4a9f0-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a9f0-122">See also</span></span>



[<span data-ttu-id="4a9f0-123">Outlook MAPI 引用入门</span><span class="sxs-lookup"><span data-stu-id="4a9f0-123">Getting Started with the Outlook MAPI Reference</span></span>](getting-started-with-the-outlook-mapi-reference.md)

