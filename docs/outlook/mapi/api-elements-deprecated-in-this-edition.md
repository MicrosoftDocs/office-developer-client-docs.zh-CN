---
title: 此版本中弃用的 API 元素
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d0a6d182-961c-4496-a3bd-f643612527a5
description: 上次修改时间：2012 年 6 月 25 日
ms.openlocfilehash: abfe734ad8af436f52fc0308d0cd236078bb47df
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32318204"
---
# <a name="api-elements-deprecated-in-this-edition"></a><span data-ttu-id="188cf-103">此版本中弃用的 API 元素</span><span class="sxs-lookup"><span data-stu-id="188cf-103">API Elements Deprecated in This Edition</span></span>

  
  
<span data-ttu-id="188cf-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="188cf-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="188cf-105">以下 API 元素在 Microsoft Outlook 2013 中已弃用。</span><span class="sxs-lookup"><span data-stu-id="188cf-105">The following API elements are deprecated in Microsoft Outlook 2013.</span></span> <span data-ttu-id="188cf-106">它们不再受支持, 不应在新项目中使用它们。</span><span class="sxs-lookup"><span data-stu-id="188cf-106">They are no longer supported and you should not use them in new projects.</span></span>
  
## <a name="deprecation-of-message-and-recipient-options"></a><span data-ttu-id="188cf-107">邮件和收件人选项的弃用</span><span class="sxs-lookup"><span data-stu-id="188cf-107">Deprecation of Message and Recipient Options</span></span>

<span data-ttu-id="188cf-108">由于过时的邮件和收件人选项, 此版本中弃用了以下 API 元素:</span><span class="sxs-lookup"><span data-stu-id="188cf-108">The following API elements are deprecated in this release because of obsolete message and recipient options:</span></span>
  
- <span data-ttu-id="188cf-109">**IXPLogon:: RegisterOptions**— MAPI 子系统不再会调用此方法来为传输提供程序建立邮件和收件人选项的任何默认值。</span><span class="sxs-lookup"><span data-stu-id="188cf-109">**IXPLogon::RegisterOptions**—The MAPI subsystem no longer calls this method to establish any default values for message and recipient options for a transport provider.</span></span>
    
- <span data-ttu-id="188cf-110">**OPTIONDATA**—支持邮件和收件人选项的属性的此数据结构已过时。</span><span class="sxs-lookup"><span data-stu-id="188cf-110">**OPTIONDATA**—This data structure that supported properties for message and recipient options is obsolete.</span></span> <span data-ttu-id="188cf-111">MAPI 子系统不再调用**IXPLogon:: RegisterOptions**以获取传输提供程序为特定地址类型支持的任何邮件或收件人选项。</span><span class="sxs-lookup"><span data-stu-id="188cf-111">The MAPI subsystem no longer calls **IXPLogon::RegisterOptions** to obtain any message or recipient options that a transport provider supports for a particular address type.</span></span> 
    
- <span data-ttu-id="188cf-112">**OPTIONCALLBACK**—此函数原型, 它是一个用于声明回调函数的传输提供程序, 后者又是用于解析提供程序属性的 MAPI 子系统已过时。</span><span class="sxs-lookup"><span data-stu-id="188cf-112">**OPTIONCALLBACK**—This function prototype, which a transport provider used to declare a callback function and which, in turn, the MAPI subsystem used to resolve the provider's properties, is obsolete.</span></span> <span data-ttu-id="188cf-113">MAPI 子系统不再调用**IXPLogon:: RegisterOptions**或使用传输提供程序返回的任何回调函数。</span><span class="sxs-lookup"><span data-stu-id="188cf-113">The MAPI subsystem no longer calls **IXPLogon::RegisterOptions** or uses any callback function returned by the transport provider.</span></span> 
    
- <span data-ttu-id="188cf-114">**IMAPISession:: MessageOptions**-MAPI 客户端和服务提供程序不应再调用此方法来显示属性, 或允许用户设置控制特定邮件和地址类型的属性。</span><span class="sxs-lookup"><span data-stu-id="188cf-114">**IMAPISession::MessageOptions**—MAPI client and service providers should no longer call this method to display properties or let users set properties that control a particular message and address type.</span></span> <span data-ttu-id="188cf-115">该方法始终返回 MAPI_E_NOT_FOUND, 指示没有适用于特定邮件的任何邮件选项。</span><span class="sxs-lookup"><span data-stu-id="188cf-115">The method always returns MAPI_E_NOT_FOUND, which indicates that there are no message options for the particular message.</span></span>
    
- <span data-ttu-id="188cf-116">**IMAPISession:: QueryDefaultMessageOpt**-MAPI 客户端和服务提供程序不应再调用此方法来检索控制特定地址类型的邮件选项的属性。</span><span class="sxs-lookup"><span data-stu-id="188cf-116">**IMAPISession::QueryDefaultMessageOpt**—MAPI client and service providers should no longer call this method to retrieve properties that control message options for a particular address type.</span></span> <span data-ttu-id="188cf-117">方法不再返回指向任何属性值数组的指针。</span><span class="sxs-lookup"><span data-stu-id="188cf-117">The method no longer returns a pointer to any array of property values.</span></span>
    
- <span data-ttu-id="188cf-118">**IAddrBook:: RecipOptions**-MAPI 客户端和服务提供程序不应再调用此方法来显示属性, 或允许用户设置控制特定地址类型的收件人处理的属性。</span><span class="sxs-lookup"><span data-stu-id="188cf-118">**IAddrBook::RecipOptions**—MAPI client and service providers should no longer call this method to display properties or let users set properties that control processing for a recipient of a particular address type.</span></span> <span data-ttu-id="188cf-119">该方法始终返回 MAPI_W_ERRORS_RETURNED, 表示特定收件人没有收件人选项。</span><span class="sxs-lookup"><span data-stu-id="188cf-119">The method always returns MAPI_W_ERRORS_RETURNED, which indicates that there are no recipient options for the particular recipient.</span></span>
    
- <span data-ttu-id="188cf-120">**IAddrBook:: QueryDefaultRecipOpt**-MAPI 客户端和服务提供程序不应再调用此方法来检索控制特定地址类型的收件人选项的属性。</span><span class="sxs-lookup"><span data-stu-id="188cf-120">**IAddrBook::QueryDefaultRecipOpt**—MAPI client and service providers should no longer call this method to retrieve properties that control recipient options for a particular address type.</span></span> <span data-ttu-id="188cf-121">方法不再返回指向任何属性值数组的指针。</span><span class="sxs-lookup"><span data-stu-id="188cf-121">The method no longer returns a pointer to any array of property values.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="188cf-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="188cf-122">See also</span></span>



[<span data-ttu-id="188cf-123">Outlook MAPI 引用入门</span><span class="sxs-lookup"><span data-stu-id="188cf-123">Getting Started with the Outlook MAPI Reference</span></span>](getting-started-with-the-outlook-mapi-reference.md)

