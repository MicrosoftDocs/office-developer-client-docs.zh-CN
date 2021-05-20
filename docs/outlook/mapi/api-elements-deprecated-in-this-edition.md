---
title: 此版本中弃用 API 元素
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d0a6d182-961c-4496-a3bd-f643612527a5
description: 上次修改时间：2012 年 6 月 25 日
ms.openlocfilehash: abfe734ad8af436f52fc0308d0cd236078bb47df
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436886"
---
# <a name="api-elements-deprecated-in-this-edition"></a><span data-ttu-id="38cc8-103">此版本中弃用 API 元素</span><span class="sxs-lookup"><span data-stu-id="38cc8-103">API Elements Deprecated in This Edition</span></span>

  
  
<span data-ttu-id="38cc8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="38cc8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="38cc8-105">以下 API 元素在 Microsoft Outlook 2013 中已弃Microsoft Outlook 2013。</span><span class="sxs-lookup"><span data-stu-id="38cc8-105">The following API elements are deprecated in Microsoft Outlook 2013.</span></span> <span data-ttu-id="38cc8-106">它们不再受支持，不应在新项目中使用它们。</span><span class="sxs-lookup"><span data-stu-id="38cc8-106">They are no longer supported and you should not use them in new projects.</span></span>
  
## <a name="deprecation-of-message-and-recipient-options"></a><span data-ttu-id="38cc8-107">弃用邮件和收件人选项</span><span class="sxs-lookup"><span data-stu-id="38cc8-107">Deprecation of Message and Recipient Options</span></span>

<span data-ttu-id="38cc8-108">由于邮件和收件人选项过时，此版本中弃用以下 API 元素：</span><span class="sxs-lookup"><span data-stu-id="38cc8-108">The following API elements are deprecated in this release because of obsolete message and recipient options:</span></span>
  
- <span data-ttu-id="38cc8-109">**IXPLogon：：RegisterOptions**- MAPI 子系统不再调用此方法来为传输提供程序的邮件和收件人选项建立任何默认值。</span><span class="sxs-lookup"><span data-stu-id="38cc8-109">**IXPLogon::RegisterOptions**—The MAPI subsystem no longer calls this method to establish any default values for message and recipient options for a transport provider.</span></span>
    
- <span data-ttu-id="38cc8-110">**OPTIONDATA** 支持邮件和收件人选项属性的此数据结构已过时。</span><span class="sxs-lookup"><span data-stu-id="38cc8-110">**OPTIONDATA**—This data structure that supported properties for message and recipient options is obsolete.</span></span> <span data-ttu-id="38cc8-111">MAPI 子系统不再调用 **IXPLogon：：RegisterOptions** 来获取传输提供程序支持的特定地址类型的任何邮件或收件人选项。</span><span class="sxs-lookup"><span data-stu-id="38cc8-111">The MAPI subsystem no longer calls **IXPLogon::RegisterOptions** to obtain any message or recipient options that a transport provider supports for a particular address type.</span></span> 
    
- <span data-ttu-id="38cc8-112">**OPTIONCALLBACK** 此函数原型（传输提供程序用于声明回调函数，而用于解析提供程序属性的 MAPI 子系统）已过时。</span><span class="sxs-lookup"><span data-stu-id="38cc8-112">**OPTIONCALLBACK**—This function prototype, which a transport provider used to declare a callback function and which, in turn, the MAPI subsystem used to resolve the provider's properties, is obsolete.</span></span> <span data-ttu-id="38cc8-113">MAPI 子系统不再调用 **IXPLogon：：RegisterOptions** 或使用传输提供程序返回的任何回调函数。</span><span class="sxs-lookup"><span data-stu-id="38cc8-113">The MAPI subsystem no longer calls **IXPLogon::RegisterOptions** or uses any callback function returned by the transport provider.</span></span> 
    
- <span data-ttu-id="38cc8-114">**IMAPISession：：MessageOptions** MAPI 客户端和服务提供商不应再调用此方法来显示属性或允许用户设置控制特定邮件和地址类型的属性。</span><span class="sxs-lookup"><span data-stu-id="38cc8-114">**IMAPISession::MessageOptions**—MAPI client and service providers should no longer call this method to display properties or let users set properties that control a particular message and address type.</span></span> <span data-ttu-id="38cc8-115">方法始终返回 MAPI_E_NOT_FOUND，这表示没有特定邮件的邮件选项。</span><span class="sxs-lookup"><span data-stu-id="38cc8-115">The method always returns MAPI_E_NOT_FOUND, which indicates that there are no message options for the particular message.</span></span>
    
- <span data-ttu-id="38cc8-116">**IMAPISession：：QueryDefaultMessageOpt**- MAPI 客户端和服务提供商不应再调用此方法来检索控制特定地址类型的邮件选项的属性。</span><span class="sxs-lookup"><span data-stu-id="38cc8-116">**IMAPISession::QueryDefaultMessageOpt**—MAPI client and service providers should no longer call this method to retrieve properties that control message options for a particular address type.</span></span> <span data-ttu-id="38cc8-117">方法不再返回指向任何属性值数组的指针。</span><span class="sxs-lookup"><span data-stu-id="38cc8-117">The method no longer returns a pointer to any array of property values.</span></span>
    
- <span data-ttu-id="38cc8-118">**IAddrBook：：RecipOptions** MAPI 客户端和服务提供商不应再调用此方法来显示属性或允许用户设置用于控制特定地址类型收件人处理的属性。</span><span class="sxs-lookup"><span data-stu-id="38cc8-118">**IAddrBook::RecipOptions**—MAPI client and service providers should no longer call this method to display properties or let users set properties that control processing for a recipient of a particular address type.</span></span> <span data-ttu-id="38cc8-119">方法始终返回MAPI_W_ERRORS_RETURNED，这表示没有特定收件人的收件人选项。</span><span class="sxs-lookup"><span data-stu-id="38cc8-119">The method always returns MAPI_W_ERRORS_RETURNED, which indicates that there are no recipient options for the particular recipient.</span></span>
    
- <span data-ttu-id="38cc8-120">**IAddrBook：：QueryDefaultRecipOpt** MAPI 客户端和服务提供商不应再调用此方法来检索控制特定地址类型的收件人选项的属性。</span><span class="sxs-lookup"><span data-stu-id="38cc8-120">**IAddrBook::QueryDefaultRecipOpt**—MAPI client and service providers should no longer call this method to retrieve properties that control recipient options for a particular address type.</span></span> <span data-ttu-id="38cc8-121">方法不再返回指向任何属性值数组的指针。</span><span class="sxs-lookup"><span data-stu-id="38cc8-121">The method no longer returns a pointer to any array of property values.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="38cc8-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38cc8-122">See also</span></span>



[<span data-ttu-id="38cc8-123">Outlook MAPI 引用入门</span><span class="sxs-lookup"><span data-stu-id="38cc8-123">Getting Started with the Outlook MAPI Reference</span></span>](getting-started-with-the-outlook-mapi-reference.md)

