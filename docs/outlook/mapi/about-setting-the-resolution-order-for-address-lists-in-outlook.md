---
title: 关于在 Outlook 中设置地址列表的解析顺序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: e1589568-cb49-86dd-5d16-b08c8117bd17
description: 上次修改时间： 2012 年 7 月 5 日
ms.openlocfilehash: 22d56ffac5d9d628b04e364fa772ddc8de488a31
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578652"
---
# <a name="about-setting-the-resolution-order-for-address-lists-in-outlook"></a><span data-ttu-id="676de-103">关于在 Outlook 中设置地址列表的解析顺序</span><span class="sxs-lookup"><span data-stu-id="676de-103">About Setting the Resolution Order for Address Lists in Outlook</span></span>

  
  
<span data-ttu-id="676de-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="676de-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="676de-105">对于每个配置文件，Microsoft Office Outlook 支持多个地址列表和用户可以手动指定消息和会议请求中的与会者都已解析通过电子邮件中的收件人的地址列表的顺序。</span><span class="sxs-lookup"><span data-stu-id="676de-105">For each profile, Microsoft Office Outlook supports multiple address lists and users can manually specify the order of address lists by which recipients in email messages and attendees in meeting requests are resolved.</span></span> <span data-ttu-id="676de-106">例如，您可以设置解析顺序，以便姓名均已解析，首先对 Outlook 通讯簿，然后针对全局地址列表。</span><span class="sxs-lookup"><span data-stu-id="676de-106">For example, you can set the resolution order so that names are resolved first against your Outlook Address Book, and then against the Global Address List.</span></span> <span data-ttu-id="676de-107">计算机上，用户可以打开通讯簿，单击**工具**和**选项**，以指定此解决方案顺序。</span><span class="sxs-lookup"><span data-stu-id="676de-107">On a computer, a user can open the Address Book, click **Tools** and then **Options** to specify this resolution order.</span></span> <span data-ttu-id="676de-108">但是，在企业环境中，是面向 IT 管理员以编程方式设置按其姓名均已解析的地址列表的顺序更有效。</span><span class="sxs-lookup"><span data-stu-id="676de-108">However, in a corporate environment, it is more efficient for IT administrators to programmatically set the order of address lists by which names are resolved.</span></span> <span data-ttu-id="676de-109">此类代码可以用作管理员部署在公司内启动自动化脚本的一部分。</span><span class="sxs-lookup"><span data-stu-id="676de-109">Such code can be used as part of a startup automation script that an administrator deploys inside the corporation.</span></span> 
  
<span data-ttu-id="676de-110">MAPI 支持在**[IAddrBook](iaddrbookimapiprop.md)** 界面中，以便您可以用于名称解析配置文件中设置新的搜索路径**[SetSearchPath](iaddrbook-getsearchpath.md)** 方法。</span><span class="sxs-lookup"><span data-stu-id="676de-110">MAPI supports the **[SetSearchPath](iaddrbook-getsearchpath.md)** method in the **[IAddrBook](iaddrbookimapiprop.md)** interface, which allows you to set a new search path in the profile that is used for name resolution.</span></span> <span data-ttu-id="676de-111">若要使用的**IAddrBook::SetSearchPath**方法，您必须指定所需要的分辨率顺序使用数组包含容器的相关地址簿解决它们的顺序。</span><span class="sxs-lookup"><span data-stu-id="676de-111">To use the **IAddrBook::SetSearchPath** method, you must specify the desired resolution order by using an array that holds containers of the relevant address books in the order they should be resolved.</span></span> <span data-ttu-id="676de-112">该数组中的每个条目还应包含相应的通讯簿的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="676de-112">Each entry in that array should also contain the entry ID of the corresponding address book.</span></span> 
  
<span data-ttu-id="676de-113">下面是如何指定地址列表的自定义的搜索路径的代码示例。</span><span class="sxs-lookup"><span data-stu-id="676de-113">The following are code examples of how to specify a custom search path for address lists.</span></span>
  
- [<span data-ttu-id="676de-114">以编程方式设置地址列表的解析顺序</span><span class="sxs-lookup"><span data-stu-id="676de-114">Programmatically Set the Resolution Order for Address Lists</span></span>](how-to-programmatically-set-the-resolution-order-for-address-lists.md)
    
- [<span data-ttu-id="676de-115">KB 292590： 如何更改与 SetSearchPath 通讯簿排序顺序</span><span class="sxs-lookup"><span data-stu-id="676de-115">KB 292590: How To Change Address Book Sort Order with SetSearchPath</span></span>](http://support.microsoft.com/kb/292590)
    

