---
title: 传输中性封装格式 (TNEF)
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 98d4fe3c-3908-4cd2-bfdb-ff1874a80b24
description: 上次修改时间：2013 年 3 月 12 日
ms.openlocfilehash: d902039fa1081e30947ddd8f70ead9ae7acec06a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356628"
---
# <a name="transport-neutral-encapsulation-format-tnef"></a><span data-ttu-id="ec30e-103">传输中性封装格式 (TNEF)</span><span class="sxs-lookup"><span data-stu-id="ec30e-103">Transport-Neutral Encapsulation Format (TNEF)</span></span>

 
  
<span data-ttu-id="ec30e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ec30e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ec30e-105">TNEF 是用于将一组 MAPI 属性（MAPI 邮件）转换为串行数据流的一种格式。</span><span class="sxs-lookup"><span data-stu-id="ec30e-105">TNEF is a format for converting a set of MAPI properties—a MAPI message—into a serial data stream.</span></span> <span data-ttu-id="ec30e-106">TNEF 函数主要由传输提供程序使用, 这些传输提供程序需要对 MAPI 邮件属性进行编码, 以便通过不支持直接支持这些属性的邮件系统进行传输。</span><span class="sxs-lookup"><span data-stu-id="ec30e-106">The TNEF functions are primarily used by transport providers that need to encode MAPI message properties for transmission through a messaging system that does not support those properties directly.</span></span> <span data-ttu-id="ec30e-107">例如, 基于 smtp 的传输使用 TNEF 对属性 (如**PR_SENT_REPRESENTING_NAME** ([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md))) 进行编码, 这在 SMTP 邮件的结构中没有直接表示。</span><span class="sxs-lookup"><span data-stu-id="ec30e-107">For example, an SMTP-based transport uses TNEF to encode properties like **PR_SENT_REPRESENTING_NAME** ([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md)), which do not have direct representations in the structure of an SMTP message.</span></span>
  
<span data-ttu-id="ec30e-108">TNEF 实现定义了几个特定于 TNEF 的属性, 每个属性都对应于特定的 MAPI 属性。</span><span class="sxs-lookup"><span data-stu-id="ec30e-108">The TNEF implementation defines several TNEF-specific attributes, each of which corresponds to a particular MAPI property.</span></span> <span data-ttu-id="ec30e-109">这些属性用于将其各自的 MAPI 属性编码为 TNEF 流。</span><span class="sxs-lookup"><span data-stu-id="ec30e-109">These attributes are used to encode their respective MAPI properties into the TNEF stream.</span></span> <span data-ttu-id="ec30e-110">此外, 还定义了一个特殊属性, 可用于封装任何不具有对应的特定属性的 MAPI 属性。</span><span class="sxs-lookup"><span data-stu-id="ec30e-110">In addition, a special attribute is defined that can be used to encapsulate any MAPI property that does not have a specific attribute corresponding to it.</span></span> <span data-ttu-id="ec30e-111">定义这些属性 (而不是简单地对所有 MAPI 属性使用统一编码方法) 的原因是, 可以与使用 TNEF 的非 MAPI 兼容软件实现向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="ec30e-111">The reason these attributes are defined — instead of simply using a uniform encoding method for all MAPI properties — is to enable backward compatibility with non-MAPI-compliant software that is using TNEF.</span></span>
  
<span data-ttu-id="ec30e-112">本部分的其余部分介绍了 TNEF 流的结构和语法、MAPI 属性和 TNEF 属性之间的映射以及某些 TNEF 属性的重要注意事项。</span><span class="sxs-lookup"><span data-stu-id="ec30e-112">The remainder of this section describes the structure and syntax of a TNEF stream, the mapping between MAPI properties and TNEF attributes, and important considerations for certain TNEF attributes.</span></span>
  

