---
title: 别名缓存
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 2813c102-6778-4443-ab4b-b573f3568705
description: '上次修改时间: 2013 年1月30日'
ms.openlocfilehash: 841b01ae8dfcf841b0a1d64113ce7258c4c61583
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334515"
---
# <a name="nickname-cache"></a><span data-ttu-id="e8265-103">别名缓存</span><span class="sxs-lookup"><span data-stu-id="e8265-103">Nickname cache</span></span>

 
  
<span data-ttu-id="e8265-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e8265-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e8265-105">microsoft Office Outlook 2007、microsoft outlook 2010 和 microsoft outlook 2013 与昵称缓存进行交互 (也称为 "自动完成流")。</span><span class="sxs-lookup"><span data-stu-id="e8265-105">Microsoft Office Outlook 2007, Microsoft Outlook 2010, and Microsoft Outlook 2013 interact with the nickname cache, also known as the "autocomplete stream."</span></span> <span data-ttu-id="e8265-106">"自动完成" 流是 Outlook 在其中保留自动完成列表, 该列表是用户撰写电子邮件时在 "**收件人**"、 **"抄送**" 和 **"密件抄送**" 编辑框中显示的名称的列表。</span><span class="sxs-lookup"><span data-stu-id="e8265-106">The autocomplete stream is where Outlook persists the autocomplete list, which is the list of names that displays in the **To**, **Cc**, and **Bcc** edit boxes while a user is composing an email.</span></span> <span data-ttu-id="e8265-107">本主题介绍 outlook 2007、outlook 2010 和 outlook 2013 如何与自动完成流交互, 还讨论文件的二进制格式以及与自动完成流交互的建议方式。</span><span class="sxs-lookup"><span data-stu-id="e8265-107">This topic describes how Outlook 2007, Outlook 2010, and Outlook 2013 interact with the autocomplete stream and also discusses the binary format of the file and the recommended ways for interacting with the autocomplete stream.</span></span> 
  
<span data-ttu-id="e8265-108">对于与 outlook 2010 或 outlook 2013 交互的应用程序, 自动完成流将存储为 mapi 属性, 并且可以使用 mapi 或邮件的**PropertyAccessor**对象进行修改。</span><span class="sxs-lookup"><span data-stu-id="e8265-108">For applications that interact with Outlook 2010 or Outlook 2013, the autocomplete stream is stored as a MAPI property and can be modified using the MAPI or the **PropertyAccessor** object of the message.</span></span> <span data-ttu-id="e8265-109">**PropertyAccessor**对象在 outlook 2010 或 outlook 2013 对象模型中公开。</span><span class="sxs-lookup"><span data-stu-id="e8265-109">The **PropertyAccessor** object is exposed in the Outlook 2010 or Outlook 2013 object models.</span></span> 
  
<span data-ttu-id="e8265-110">Outlook 2007 对象模型或 MAPI api 没有依存关系。</span><span class="sxs-lookup"><span data-stu-id="e8265-110">There are no dependencies on the Outlook 2007 object model or MAPI APIs.</span></span> <span data-ttu-id="e8265-111">因此, 可以使用任何编程语言编写对 Outlook 2007 中的自动完成流进行更改的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e8265-111">Therefore, applications that make changes to the autocomplete stream within Outlook 2007 can be written using any programming language.</span></span>
  
## <a name="interacting-with-the-autocomplete-stream"></a><span data-ttu-id="e8265-112">与自动完成流交互</span><span class="sxs-lookup"><span data-stu-id="e8265-112">Interacting with the Autocomplete Stream</span></span>

<span data-ttu-id="e8265-113">当邮件上的 "**收件人**"、 **"抄送**" 或 **"密件抄送**" 编辑框被访问时, 将加载自动完成流并显示用户名列表。</span><span class="sxs-lookup"><span data-stu-id="e8265-113">When the **To**, **Cc**, or **Bcc** edit boxes are accessed on a message, the autocomplete stream is loaded and the list of user names is displayed.</span></span> <span data-ttu-id="e8265-114">Outlook 通过以下两种方式与自动完成流进行交互:</span><span class="sxs-lookup"><span data-stu-id="e8265-114">Outlook interacts with the autocomplete stream in two ways:</span></span> 
  
1. <span data-ttu-id="e8265-115">加载自动完成流</span><span class="sxs-lookup"><span data-stu-id="e8265-115">Loading the autocomplete stream</span></span> 
    
2. <span data-ttu-id="e8265-116">保存对自动完成流中的数据的更改</span><span class="sxs-lookup"><span data-stu-id="e8265-116">Saving changes to the data in the autocomplete stream</span></span>
    
<span data-ttu-id="e8265-117">存储自动完成数据的方法在 outlook 2007 和 outlook 2010 或 outlook 2013 之间有所不同, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="e8265-117">The means of storing the autocomplete data differs between Outlook 2007 and Outlook 2010 or Outlook 2013 as follows:</span></span> 
  
 <span data-ttu-id="e8265-118">**Outlook 2007**</span><span class="sxs-lookup"><span data-stu-id="e8265-118">**Outlook 2007**</span></span>
  
<span data-ttu-id="e8265-119">对于 Outlook 2007, 自动完成流存储在与配置文件同名的文件中, 扩展名为 nk2。</span><span class="sxs-lookup"><span data-stu-id="e8265-119">For Outlook 2007, the autocomplete stream is stored in a file with the same name as the profile and an extension of .nk2.</span></span> <span data-ttu-id="e8265-120">例如, 如果使用的是默认的 "outlook" 配置文件, 则该文件将被称为 "nk2"。</span><span class="sxs-lookup"><span data-stu-id="e8265-120">For example, if the default profile of "outlook" is used, the file will be called "outlook.nk2".</span></span> <span data-ttu-id="e8265-121">. nk2 文件存储在%APPDATA%\Microsoft\Outlook. 中。</span><span class="sxs-lookup"><span data-stu-id="e8265-121">The .nk2 file is stored in %APPDATA%\Microsoft\Outlook.</span></span> <span data-ttu-id="e8265-122">有关昵称缓存二进制文件格式的详细信息, 请参阅[Outlook 2003/2007 NK2 文件格式和开发人员指南](https://portalvhds6gyn3khqwmgzd.blob.core.windows.net/files/NK2/NK2WithBinaryExample.pdf)。</span><span class="sxs-lookup"><span data-stu-id="e8265-122">For more information about the nickname cache binary file format, see [Outlook 2003/2007 NK2 File Format and Developer Guidelines](https://portalvhds6gyn3khqwmgzd.blob.core.windows.net/files/NK2/NK2WithBinaryExample.pdf).</span></span>
  
 <span data-ttu-id="e8265-123">**outlook 2010 和 outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="e8265-123">**Outlook 2010 and Outlook 2013**</span></span>
  
<span data-ttu-id="e8265-124">outlook 2010 或 outlook 2013 从邮件帐户的送达存储区的 "收件箱" 的 "关联内容" 表中的邮件中读取自动完成流。</span><span class="sxs-lookup"><span data-stu-id="e8265-124">Outlook 2010 or Outlook 2013 reads the autocomplete stream from a message in the Associated Contents table of the Inbox of the mail account's delivery store.</span></span> <span data-ttu-id="e8265-125">此隐藏邮件具有 IPM 的邮件类和主题。配置。自动完成。</span><span class="sxs-lookup"><span data-stu-id="e8265-125">This hidden message has a message class and subject of IPM.Configuration.Autocomplete.</span></span> <span data-ttu-id="e8265-126">自动完成流存储在此邮件的 PR_ROAMING_BINARYSTREAM 属性 ([PidTagRoamingBinary 规范属性](pidtagroamingbinary-canonical-property.md)) 中。</span><span class="sxs-lookup"><span data-stu-id="e8265-126">The autocomplete stream is stored on this message in the PR_ROAMING_BINARYSTREAM property ([PidTagRoamingBinary Canonical Property](pidtagroamingbinary-canonical-property.md)).</span></span> <span data-ttu-id="e8265-127">自动完成数据可能会暂时缓存在%USERPROFILE%\AppData\Local\Microsoft\Outlook\RoamCache. 中的 "自动完成" .dat 文件中。</span><span class="sxs-lookup"><span data-stu-id="e8265-127">The autocomplete data may be temporarily cached in an autocomplete .dat file located in %USERPROFILE%\AppData\Local\Microsoft\Outlook\RoamCache.</span></span> <span data-ttu-id="e8265-128">但是, 该 .dat 文件只是一个缓存, 在用户退出 Outlook 2010 或 Outlook 2013 时不用于写回到传递存储。</span><span class="sxs-lookup"><span data-stu-id="e8265-128">However, the .dat file is only a cache and is not used to write back to the delivery store when the user exits Outlook 2010 or Outlook 2013.</span></span>
  
## <a name="loading-the-autocomplete-stream"></a><span data-ttu-id="e8265-129">加载自动完成流</span><span class="sxs-lookup"><span data-stu-id="e8265-129">Loading the Autocomplete Stream</span></span>

<span data-ttu-id="e8265-130">每当初始化具有寻址功能的项时, Outlook 都会加载自动完成流。</span><span class="sxs-lookup"><span data-stu-id="e8265-130">Outlook loads the autocomplete stream whenever an item with addressing functionality is initialized.</span></span> <span data-ttu-id="e8265-131">例如, 电子邮件地址用于新邮件、邮件答复、联系人项目、会议请求等。</span><span class="sxs-lookup"><span data-stu-id="e8265-131">For example, email addresses are used in a new mail, a mail reply, a contact item, a meeting request, and so on.</span></span> <span data-ttu-id="e8265-132">若要加载数据, Outlook 会将流的所有内容读取到内存中。</span><span class="sxs-lookup"><span data-stu-id="e8265-132">To load the data, Outlook reads all of the contents of the stream into memory.</span></span>
  
<span data-ttu-id="e8265-133">对于自动完成操作, outlook 在 outlook .exe 进程生存期内以独占方式与此内存中的结构交互。</span><span class="sxs-lookup"><span data-stu-id="e8265-133">For autocomplete operations, Outlook interacts exclusively with this in-memory structure for the duration of the outlook.exe process lifetime.</span></span> <span data-ttu-id="e8265-134">Outlook 仅在关闭时保存该结构。</span><span class="sxs-lookup"><span data-stu-id="e8265-134">Outlook only saves the structure on shutdown.</span></span> <span data-ttu-id="e8265-135">有关此过程的详细信息, 请参阅以下部分 "保存自动完成流"。</span><span class="sxs-lookup"><span data-stu-id="e8265-135">See the following section "Saving the Autocomplete Stream" for more information on this process.</span></span>
  
## <a name="saving-the-autocomplete-stream"></a><span data-ttu-id="e8265-136">保存自动完成流</span><span class="sxs-lookup"><span data-stu-id="e8265-136">Saving the Autocomplete Stream</span></span>

<span data-ttu-id="e8265-137">如果自动完成列表已通过以下任一方式发生更改, Outlook 会在关闭时保存自动完成流:</span><span class="sxs-lookup"><span data-stu-id="e8265-137">Outlook saves the autocomplete stream on shutdown if the autocomplete list has changed in any of the following ways:</span></span>
  
- <span data-ttu-id="e8265-138">通过解析名称, 从 "通讯簿" 对话框中选取收件人, 或将邮件发送到列表中尚未列出的收件人, 添加一个新的昵称条目。</span><span class="sxs-lookup"><span data-stu-id="e8265-138">A new nickname entry is added through resolving a name, picking a recipient from the address book dialog, or sending mail to a recipient that was not already in the list.</span></span>
    
- <span data-ttu-id="e8265-139">通过将邮件发送到列表中的现有收件人来修改条目。</span><span class="sxs-lookup"><span data-stu-id="e8265-139">An entry is modified by sending mail to an existing recipient in the list.</span></span>
    
- <span data-ttu-id="e8265-140">用户通过 UI 删除条目。</span><span class="sxs-lookup"><span data-stu-id="e8265-140">An entry is removed by the user through the UI.</span></span>
    
- <span data-ttu-id="e8265-141">与本主题不相关的其他次要方案。</span><span class="sxs-lookup"><span data-stu-id="e8265-141">Other minor scenarios not relevant to this topic.</span></span>
    
<span data-ttu-id="e8265-142">保存对自动完成数据的更改涉及将内存中的结构写回到[自动完成流](autocomplete-stream.md)中。</span><span class="sxs-lookup"><span data-stu-id="e8265-142">Saving changes to the autocomplete data involves writing the in-memory structure back to an [Autocomplete Stream](autocomplete-stream.md).</span></span> <span data-ttu-id="e8265-143">在与 Outlook 2007 交互时, 会将该流保存到 nk2 文件中。</span><span class="sxs-lookup"><span data-stu-id="e8265-143">When interacting with Outlook 2007, the stream is saved to a local .nk2 file.</span></span> <span data-ttu-id="e8265-144">对于 outlook 2010 或 outlook 2013, 自动完成流会写回到邮件帐户的送达存储区的 "收件箱" 的 "关联的内容" 表中。</span><span class="sxs-lookup"><span data-stu-id="e8265-144">For Outlook 2010 or Outlook 2013, the autocomplete stream writes back to the Associated Contents table of the Inbox of the mail account's delivery store.</span></span>
  
## <a name="recommendations"></a><span data-ttu-id="e8265-145">建议</span><span class="sxs-lookup"><span data-stu-id="e8265-145">Recommendations</span></span>

- <span data-ttu-id="e8265-146">从不部分修改自动完成流。</span><span class="sxs-lookup"><span data-stu-id="e8265-146">Never partially modify the autocomplete stream.</span></span> <span data-ttu-id="e8265-147">受支持的交互为 1) 将整个自动完成流读取到内存, 2)。修改内存结构和 3) 将整个流写入邮件帐户的传递存储收件箱的 "关联的内容" 表 (对于 Outlook 2010 或outlook 2013) 或本地 nk2 文件 (outlook 2007)。</span><span class="sxs-lookup"><span data-stu-id="e8265-147">The supported interaction is to 1) read the entire autocomplete stream into memory, 2) modify the memory structure, and 3) write the entire stream back to either the Associated Contents table of the Inbox of the mail account's delivery store (for Outlook 2010 or Outlook 2013) or to the local .nk2 file (Outlook 2007).</span></span>
    
- <span data-ttu-id="e8265-148">当 Outlook 正在运行时, 请勿与自动完成流进行交互。</span><span class="sxs-lookup"><span data-stu-id="e8265-148">Do not interact with the autocomplete stream while Outlook is running.</span></span> <span data-ttu-id="e8265-149">如果在您修改流时 Outlook 正在运行, 则它可能会在您的更改关闭时覆盖您所做的更改。</span><span class="sxs-lookup"><span data-stu-id="e8265-149">If Outlook is running while you modify the stream, it will likely overwrite your changes when it shuts down.</span></span>
    
- <span data-ttu-id="e8265-150">请勿将类型为 PT_MV_UNICODE 和 PR_MV_STRING8 的属性写入 Microsoft Outlook 2003 将使用的自动完成流中。</span><span class="sxs-lookup"><span data-stu-id="e8265-150">Do not write properties of type PT_MV_UNICODE and PR_MV_STRING8 into an autocomplete stream to be consumed by Microsoft Outlook 2003.</span></span> <span data-ttu-id="e8265-151">只有 outlook 2007、outlook 2010 和 outlook 2013 可以理解这些属性。</span><span class="sxs-lookup"><span data-stu-id="e8265-151">These properties are only understood by Outlook 2007, Outlook 2010, and Outlook 2013.</span></span>
    
- <span data-ttu-id="e8265-152">在开发与 Outlook 2007 交互的代码时, 我们建议您在使用标准文件锁定 api (例如, c/c + + 中的**LockFile**和 nk2 文件) 中的其他过程中锁定和写入文件, 然后再**进行修改。** 以 c # 为单位的 FileStream)。</span><span class="sxs-lookup"><span data-stu-id="e8265-152">When developing code that interacts with Outlook 2007, we recommend that you lock the .nk2 file from modification by other processes while you are reading and writing it using standard file locking APIs (for example, **LockFile** in C/C++ and **FileStream.Lock** in C#).</span></span> 
    
- <span data-ttu-id="e8265-153">仅修改自动完成流的行集中的类型的属性。</span><span class="sxs-lookup"><span data-stu-id="e8265-153">Only modify the properties of types that are from the row-set of the autocomplete stream.</span></span> <span data-ttu-id="e8265-154">有关自动完成流属性和属性类型的详细信息, 请参阅[自动完成流](autocomplete-stream.md)。</span><span class="sxs-lookup"><span data-stu-id="e8265-154">For more information about the autocomplete stream properties and property types, see [Autocomplete Stream](autocomplete-stream.md).</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e8265-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e8265-155">See also</span></span>



[<span data-ttu-id="e8265-156">自动完成流</span><span class="sxs-lookup"><span data-stu-id="e8265-156">Autocomplete Stream</span></span>](autocomplete-stream.md)
  
[<span data-ttu-id="e8265-157">MAPI 配置文件</span><span class="sxs-lookup"><span data-stu-id="e8265-157">MAPI Profiles</span></span>](mapi-profiles.md)


[<span data-ttu-id="e8265-158">Outlook 2003/2007 NK2 文件格式和开发人员指南</span><span class="sxs-lookup"><span data-stu-id="e8265-158">Outlook 2003/2007 NK2 File Format and Developer Guidelines</span></span>](https://portalvhds6gyn3khqwmgzd.blob.core.windows.net/files/NK2/NK2WithBinaryExample.pdf)

