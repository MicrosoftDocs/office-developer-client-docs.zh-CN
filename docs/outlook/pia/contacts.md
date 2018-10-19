---
title: 联系人
TOCTitle: Contacts
ms:assetid: e988de54-6b1e-4e83-a226-3a898903608f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184649(v=office.15)
ms:contentKeyID: 55119820
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: a172f0ab978f2281b509ed7e848168d8daa3a0fc
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406209"
---
# <a name="contacts"></a><span data-ttu-id="66187-102">联系人</span><span class="sxs-lookup"><span data-stu-id="66187-102">Contacts</span></span>

<span data-ttu-id="66187-103">本节收录了与联系人相关的示例主题。</span><span class="sxs-lookup"><span data-stu-id="66187-103">This section provides sample tasks that involve views.</span></span> <span data-ttu-id="66187-104">联系人表示要与之通信的人员和企业。</span><span class="sxs-lookup"><span data-stu-id="66187-104">Contacts represent people and businesses you want to communicate with.</span></span> <span data-ttu-id="66187-105">“联系人”文件夹中包含电子邮件通讯簿和联系人信息存储。</span><span class="sxs-lookup"><span data-stu-id="66187-105">The Contacts folder is your email address book and information storage for the contacts.</span></span> <span data-ttu-id="66187-106">[ContactItem](https://msdn.microsoft.com/library/bb644956\(v=office.15\)) 对象是 Outlook 内置对象，表示“联系人”文件夹中的唯一联系人。</span><span class="sxs-lookup"><span data-stu-id="66187-106">A [ContactItem](https://msdn.microsoft.com/library/bb644956\(v=office.15\)) object is an Outlook built-in object that represents unique contacts in a Contacts folder.</span></span> <span data-ttu-id="66187-107">**ContactItem** 对象有超过 100 个属性（如 [FirstName](https://msdn.microsoft.com/library/bb652965\(v=office.15\))、[CompanyName](https://msdn.microsoft.com/library/bb610212\(v=office.15\)) 和 [OfficeLocation](https://msdn.microsoft.com/library/bb647145\(v=office.15\))），以及在内置属性不足时创建的自定义属性。这些属性可用于存储每个联系人的相关信息。</span><span class="sxs-lookup"><span data-stu-id="66187-107">The **ContactItem** object has over 100 properties, such as [FirstName](https://msdn.microsoft.com/library/bb652965\(v=office.15\)), [CompanyName](https://msdn.microsoft.com/library/bb610212\(v=office.15\)), and [OfficeLocation](https://msdn.microsoft.com/library/bb647145\(v=office.15\)), as well as custom properties if the built-in properties are not sufficient, that you can use to store information about each contact.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="66187-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="66187-108">In this section</span></span>

|<span data-ttu-id="66187-109">主题</span><span class="sxs-lookup"><span data-stu-id="66187-109">Topic</span></span>|<span data-ttu-id="66187-110">说明</span><span class="sxs-lookup"><span data-stu-id="66187-110">Description</span></span>|
|:----|:----------|
|[<span data-ttu-id="66187-111">创建联系人项</span><span class="sxs-lookup"><span data-stu-id="66187-111">Create a Contact item</span></span>](how-to-create-a-contact-item.md)  |<span data-ttu-id="66187-112">介绍了如何创建联系人项，并设置联系人的各种属性。</span><span class="sxs-lookup"><span data-stu-id="66187-112">Creates a contact item and sets various properties for the contact.</span></span>|
|[<span data-ttu-id="66187-113">创建自定义联系人项</span><span class="sxs-lookup"><span data-stu-id="66187-113">Create a custom Contact item</span></span>](how-to-create-a-custom-contact-item.md)  |<span data-ttu-id="66187-114">介绍了如何创建自定义联系人项，并设置预定义属性和用户定义的属性。</span><span class="sxs-lookup"><span data-stu-id="66187-114">Creates a custom contact item and sets both predefined and user-defined properties.</span></span>|
|[<span data-ttu-id="66187-115">通过 vCard 文件创建联系人项，并将项保存到文件夹中</span><span class="sxs-lookup"><span data-stu-id="66187-115">Create a Contact item from a vCard file and save the item in a folder</span></span>](how-to-create-a-contact-item-from-a-vcard-file-and-save-the-item-in-a-folder.md)  |<span data-ttu-id="66187-116">介绍了如何将所有 vCard 文件导入文件系统文件夹中，并将联系人保存到 *targetFolder* 参数指定的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="66187-116">Imports all the vCard files in a file system folder and saves the contacts into the folder specified by the *targetFolder* parameter.</span></span>|

## <a name="see-also"></a><span data-ttu-id="66187-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="66187-117">See also</span></span>

- [<span data-ttu-id="66187-118">通讯簿</span><span class="sxs-lookup"><span data-stu-id="66187-118">Address Book</span></span>](address-book.md)
- [<span data-ttu-id="66187-119">电子名片</span><span class="sxs-lookup"><span data-stu-id="66187-119">Electronic Business Cards</span></span>](electronic-business-cards.md)
- [<span data-ttu-id="66187-120">邮件</span><span class="sxs-lookup"><span data-stu-id="66187-120">Mail</span></span>](mail.md)
- [<span data-ttu-id="66187-121">收件人</span><span class="sxs-lookup"><span data-stu-id="66187-121">Recipients</span></span>](recipients.md)
- [<span data-ttu-id="66187-122">我如何...（Outlook 2013 PIA 参考）</span><span class="sxs-lookup"><span data-stu-id="66187-122">How do I... (Outlook 2013 PIA reference)</span></span>](how-do-i-outlook-2013-pia-reference.md)

