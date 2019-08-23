---
title: 关于设置在 Outlook 中地址列表的解析顺序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: e1589568-cb49-86dd-5d16-b08c8117bd17
description: 上次修改时间：2012 年 7 月 5 日
ms.openlocfilehash: 07a4c3e90f686f291f95ff87f337b54d8bf35edc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321831"
---
# <a name="about-setting-the-resolution-order-for-address-lists-in-outlook"></a><span data-ttu-id="4088a-103">关于设置在 Outlook 中地址列表的解析顺序</span><span class="sxs-lookup"><span data-stu-id="4088a-103">About Setting the Resolution Order for Address Lists in Outlook</span></span>

  
  
<span data-ttu-id="4088a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4088a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4088a-105">对于每个配置文件，Microsoft Office Outlook 支持多个地址列表，用户可以手动指定地址列表的顺序，按这个顺序解析电子邮件中的收件人和会议请求中的与会者。</span><span class="sxs-lookup"><span data-stu-id="4088a-105">For each profile, Microsoft Office Outlook supports multiple address lists and users can manually specify the order of address lists by which recipients in email messages and attendees in meeting requests are resolved.</span></span> <span data-ttu-id="4088a-106">例如，可以设置解析顺序，以便先按照 Outlook 通讯簿，再按照全局地址列表解析名称。</span><span class="sxs-lookup"><span data-stu-id="4088a-106">For example, you can set the resolution order so that names are resolved first against your Outlook Address Book, and then against the Global Address List.</span></span> <span data-ttu-id="4088a-107">在计算机上，用户可以打开通讯簿，单击**工具**和**选项**指定这一解析顺序。</span><span class="sxs-lookup"><span data-stu-id="4088a-107">On a computer, a user can open the Address Book, click **Tools** and then **Options** to specify this resolution order.</span></span> <span data-ttu-id="4088a-108">但是，在企业环境中，IT 管理员以编程方式设置解析名称的地址列表顺序会更有效。</span><span class="sxs-lookup"><span data-stu-id="4088a-108">However, in a corporate environment, it is more efficient for IT administrators to programmatically set the order of address lists by which names are resolved.</span></span> <span data-ttu-id="4088a-109">此类代码可用作管理员在公司内部部署的启动自动化脚本的一部分。</span><span class="sxs-lookup"><span data-stu-id="4088a-109">Such code can be used as part of a startup automation script that an administrator deploys inside the corporation.</span></span> 
  
<span data-ttu-id="4088a-110">MAPI 支持 **[IAddrBook](iaddrbookimapiprop.md)** 界面中的 **[SetSearchPath](iaddrbook-getsearchpath.md)** 方法，允许您在用于名称解析的配置文件中设置新的搜索路径。</span><span class="sxs-lookup"><span data-stu-id="4088a-110">MAPI supports the **[SetSearchPath](iaddrbook-getsearchpath.md)** method in the **[IAddrBook](iaddrbookimapiprop.md)** interface, which allows you to set a new search path in the profile that is used for name resolution.</span></span> <span data-ttu-id="4088a-111">若要使用 **IAddrBook::SetSearchPath** 方法，您必须使用数组指定所需的解析顺序，该数组按照应该解析的顺序保存相关通讯簿的容器。</span><span class="sxs-lookup"><span data-stu-id="4088a-111">To use the **IAddrBook::SetSearchPath** method, you must specify the desired resolution order by using an array that holds containers of the relevant address books in the order they should be resolved.</span></span> <span data-ttu-id="4088a-112">该数组中的每个条目还应包含相应通讯簿的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="4088a-112">Each entry in that array should also contain the entry ID of the corresponding address book.</span></span> 
  
<span data-ttu-id="4088a-113">以下是如何指定地址列表自定义搜索路径的代码示例。</span><span class="sxs-lookup"><span data-stu-id="4088a-113">The following are code examples of how to specify a custom search path for address lists.</span></span>
  
- [<span data-ttu-id="4088a-114">以编程方式设置地址列表的解析顺序</span><span class="sxs-lookup"><span data-stu-id="4088a-114">Programmatically Set the Resolution Order for Address Lists</span></span>](how-to-programmatically-set-the-resolution-order-for-address-lists.md)
    
- [<span data-ttu-id="4088a-115">KB 292590：如何使用 SetSearchPath 更改通讯簿排序顺序</span><span class="sxs-lookup"><span data-stu-id="4088a-115">KB 292590: How To Change Address Book Sort Order with SetSearchPath</span></span>](https://support.microsoft.com/kb/292590)
    

