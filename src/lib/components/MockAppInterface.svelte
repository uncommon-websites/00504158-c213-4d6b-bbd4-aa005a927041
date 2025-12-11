<script lang="ts">
    // Mock data for the interface
    const favorites = [
        { name: "Acme Corp Website", icon: "star" },
        { name: "Mobile App Redesign", icon: "star" },
        { name: "High Priority", icon: "alert" },
        { name: "Client Reviews", icon: "doc" }
    ];

    const channels = [
        { name: "Acme Corp Website", icon: "globe", color: "bg-blue-100 text-blue-600" },
        { name: "Mobile App Redesign", icon: "phone", color: "bg-purple-100 text-purple-600" },
        { name: "E-commerce Platform", icon: "cart", color: "bg-green-100 text-green-600" },
        { name: "Brand Guidelines", icon: "palette", color: "bg-pink-100 text-pink-600" },
        { name: "Marketing Site", icon: "megaphone", color: "bg-orange-100 text-orange-600" },
        { name: "Dashboard UI", icon: "layout", color: "bg-indigo-100 text-indigo-600" },
        { name: "Landing Pages", icon: "file", color: "bg-yellow-100 text-yellow-600" },
        { name: "Client Portal", icon: "users", color: "bg-cyan-100 text-cyan-600" }
    ];

    const posts = [
        {
            title: "Hero button misaligned on mobile",
            author: "Sarah Chen",
            preview: "CTA button is 3px off center on iPhone 14. Needs to align with hero text.",
            tag: "High Priority",
            tagColor: "text-red-500",
            icon: "🔴",
            iconBg: "bg-red-50"
        },
        {
            title: "Navigation menu hover state feedback",
            author: "Mike Rodriguez",
            preview: "The hover animation feels too slow. Can we speed it up to 200ms?",
            tag: "Design",
            tagColor: "text-purple-500",
            icon: "🎨",
            iconBg: "bg-purple-50"
        },
        {
            title: "Footer links broken on staging",
            author: "Client: Acme Corp",
            preview: "Hi team, the social media links in the footer are returning 404 errors.",
            tag: "Bug",
            tagColor: "text-orange-500",
            icon: "🐛",
            iconBg: "bg-orange-50"
        },
        {
            title: "Love the new color scheme!",
            author: "Client: Acme Corp",
            preview: "The updated brand colors look amazing. Approved for production.",
            tag: "Approved",
            tagColor: "text-green-500",
            icon: "✓",
            iconBg: "bg-green-50"
        }
    ];

    const yesterdayPosts = [
        {
            title: "Typography spacing issues resolved",
            author: "Dev Team",
            preview: "Fixed the line-height inconsistencies across all heading styles. Ready for review.",
            tag: "Resolved",
            tagColor: "text-green-500",
            icon: "✓",
            iconBg: "bg-green-50"
        },
        {
            title: "Image optimization needed",
            author: "Performance Audit",
            preview: "Homepage hero images are 2.4MB. Should be under 500KB for optimal load times.",
            tag: "Performance",
            tagColor: "text-blue-500",
            icon: "⚡",
            iconBg: "bg-blue-50"
        },
        {
            title: "Client requested color adjustment",
            author: "Client: Acme Corp",
            preview: "Can we make the primary blue slightly darker? Current shade feels too light.",
            tag: "Design Change",
            tagColor: "text-purple-500",
            icon: "🎨",
            iconBg: "bg-purple-50"
        }
    ];

    const team = [
        { name: "Sarah Chen", status: "Reviewing designs", online: true, img: "https://i.pravatar.cc/150?u=sarah" },
        { name: "Mike Rodriguez", status: "In a meeting", online: true, img: "https://i.pravatar.cc/150?u=mike" },
        { name: "Alex Kim", online: true, img: "https://i.pravatar.cc/150?u=alex" },
        { name: "Jordan Taylor", online: true, img: "https://i.pravatar.cc/150?u=jordan" },
        { name: "Client: Acme Corp", online: true, img: "https://i.pravatar.cc/150?u=client1" },
        { name: "Dev Team", online: false, img: "https://i.pravatar.cc/150?u=dev" }
    ];
</script>

<div class="rounded-xl border border-gray-200 bg-white shadow-2xl overflow-hidden flex h-[800px] text-sm select-none relative z-10">
    <!-- Left Sidebar -->
    <div class="w-64 bg-gray-50 border-r border-gray-200 flex flex-col flex-shrink-0">
        <!-- Header -->
        <div class="p-3 border-b border-gray-200 flex items-center justify-between">
            <div class="flex items-center gap-2 font-medium text-gray-900">
                <svg class="w-5 h-5" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path
                        fill-rule="evenodd"
                        clip-rule="evenodd"
                        d="M6.99251 12.196C6.85314 12.5757 6.62925 12.9208 6.33682 13.2067H6.33835C6.00191 13.5351 5.58566 13.7756 5.12816 13.9059C4.67065 14.0362 4.18671 14.0522 3.72118 13.9523C3.25564 13.8524 2.82357 13.64 2.46501 13.3345C2.10645 13.0291 1.83299 12.6406 1.66998 12.2051C1.50697 11.7696 1.45969 11.3012 1.5325 10.8432C1.60532 10.3852 1.79587 9.95244 2.08653 9.58516C2.37718 9.21781 2.75852 8.9277 3.1952 8.74177C3.63188 8.55585 4.10979 8.48002 4.58462 8.52142L4.57074 8.50792C5.0567 8.54782 5.54575 8.48407 6.00378 8.32124C6.4618 8.15846 6.87776 7.90043 7.2226 7.56521C7.56746 7.22998 7.83285 6.82564 8.00036 6.38041C8.16786 5.93517 8.23344 5.45976 8.1924 4.98737L8.20628 5.00087C8.15181 4.43594 8.27796 3.86844 8.56753 3.37575C8.85701 2.88307 9.29579 2.48919 9.82407 2.24782C10.3523 2.00645 10.9443 1.92933 11.5192 2.02701C12.0942 2.12467 12.6243 2.39237 13.037 2.79358C13.4497 3.19479 13.7251 3.70999 13.8256 4.26892C13.926 4.82785 13.8467 5.4033 13.5984 5.9168C13.3501 6.4303 12.9449 6.85685 12.4381 7.13828C11.9313 7.41971 11.3474 7.54233 10.7663 7.4894L10.781 7.5029C10.2949 7.46279 9.80563 7.52632 9.34741 7.68904C8.88919 7.85176 8.47309 8.10975 8.12805 8.44499C7.78301 8.78025 7.51742 9.18466 7.34983 9.63001C7.18224 10.0754 7.11669 10.551 7.15774 11.0235L7.14309 11.01C7.1833 11.4112 7.13189 11.8162 6.99251 12.196ZM11.5077 14.7121L11.493 14.6986C11.9061 14.739 12.3232 14.6897 12.7143 14.5543C13.1053 14.4188 13.4605 14.2007 13.7542 13.9154C14.0477 13.6302 14.2726 13.285 14.4121 12.905C14.5518 12.525 14.6028 12.1196 14.5615 11.718L14.5762 11.7315C14.5351 11.2591 14.6007 10.7838 14.7681 10.3385C14.9356 9.89327 15.2011 9.48893 15.5459 9.15368C15.8908 8.8185 16.3068 8.56042 16.7648 8.39767C17.2228 8.23481 17.7118 8.17111 18.1978 8.21099L18.1832 8.19749C18.7645 8.25059 19.3485 8.12801 19.8556 7.84656C20.3627 7.56511 20.7681 7.13845 21.0165 6.62479C21.265 6.11114 21.3444 5.53548 21.2439 4.97634C21.1435 4.4172 20.868 3.9018 20.4551 3.50044C20.0422 3.09909 19.512 2.8313 18.9368 2.73364C18.3616 2.63596 17.7695 2.71315 17.241 2.95467C16.7126 3.19618 16.2737 3.59027 15.9842 4.08319C15.6946 4.57609 15.5685 5.14383 15.6232 5.70895L15.6093 5.6947C15.6504 6.16712 15.585 6.64259 15.4175 7.08788C15.2501 7.53318 14.9846 7.93758 14.6398 8.27287C14.2949 8.60805 13.8789 8.86612 13.4208 9.02888C12.9627 9.19163 12.4736 9.25523 11.9876 9.21526L12.0015 9.22951C11.5885 9.18908 11.1713 9.23836 10.7803 9.37381C10.3893 9.50919 10.034 9.72744 9.74039 10.0127C9.44674 10.2979 9.22199 10.6431 9.08234 11.0231C8.94276 11.4031 8.89176 11.8085 8.93304 12.2101L8.91915 12.1966C8.96005 12.6689 8.89439 13.1443 8.72688 13.5895C8.5593 14.0346 8.29389 14.4389 7.94908 14.7741C7.60425 15.1093 7.18835 15.3673 6.73039 15.5302C6.27242 15.693 5.78342 15.7569 5.29749 15.7171L5.31138 15.7306C4.73003 15.6775 4.14599 15.8001 3.63892 16.0815C3.13186 16.363 2.72644 16.7896 2.478 17.3033C2.22954 17.817 2.15013 18.3926 2.25061 18.9518C2.35109 19.5109 2.62657 20.0263 3.03945 20.4276C3.45234 20.829 3.98253 21.0968 4.55773 21.1944C5.13293 21.2921 5.72512 21.2149 6.25353 20.9734C6.78193 20.7319 7.22085 20.3379 7.51038 19.8449C7.79994 19.352 7.92601 18.7843 7.87139 18.2191L7.88605 18.2326C7.845 17.7602 7.91058 17.2849 8.07809 16.8396C8.24551 16.3944 8.511 15.99 8.85581 15.6548C9.20069 15.3196 9.61664 15.0615 10.0746 14.8988C10.5327 14.7359 11.0217 14.6722 11.5077 14.7121ZM17.1996 10.7633C16.9071 11.0493 16.6832 11.3944 16.5437 11.7741C16.4042 12.1538 16.3526 12.5587 16.3925 12.9601L16.3786 12.9466C16.4197 13.419 16.3541 13.8944 16.1866 14.3396C16.0191 14.7849 15.7537 15.1892 15.4089 15.5244C15.064 15.8596 14.648 16.1177 14.19 16.2804C13.732 16.4433 13.2429 16.507 12.757 16.4671L12.7708 16.4806C12.1896 16.4281 11.6057 16.551 11.0989 16.8328C10.5921 17.1145 10.1871 17.5414 9.93902 18.0551C9.69097 18.5689 9.61188 19.1444 9.71265 19.7035C9.81349 20.2625 10.0892 20.7777 10.5022 21.1788C10.9152 21.5799 11.4454 21.8474 12.0205 21.9448C12.5957 22.0423 13.1877 21.9649 13.716 21.7234C14.2443 21.4817 14.683 21.0877 14.9724 20.5947C15.2618 20.1018 15.3878 19.5342 15.3332 18.9692L15.3478 18.9827C15.3068 18.5103 15.3723 18.0349 15.5398 17.5896C15.7073 17.1444 15.9728 16.7401 16.3176 16.4048C16.6625 16.0696 17.0784 15.8115 17.5364 15.6488C17.9945 15.486 18.4835 15.4222 18.9695 15.4621L18.9548 15.4486C19.4296 15.4901 19.9076 15.4144 20.3444 15.2286C20.7811 15.0427 21.1625 14.7527 21.4533 14.3854C21.744 14.0181 21.9347 13.5854 22.0075 13.1274C22.0805 12.6694 22.0332 12.2009 21.8703 11.7653C21.7073 11.3298 21.4339 10.9413 21.0754 10.6358C20.7168 10.3303 20.2848 10.1178 19.8192 10.0179C19.3536 9.91795 18.8697 9.93385 18.4121 10.0641C17.9546 10.1945 17.5383 10.4349 17.2019 10.7633H17.1996Z"
                        fill="currentColor"
                    />
                </svg>
                BugSmash
                <svg class="w-3 h-3 text-gray-400" viewBox="0 0 16 16" fill="currentColor"><path d="M4 6l4 4 4-4" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/></svg>
            </div>
            <div class="flex items-center gap-1">
                 <svg class="w-4 h-4 text-gray-400" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><path d="M12 8v8M8 12h8"/></svg>
            </div>
        </div>

        <!-- New Feedback Button -->
        <div class="px-3 py-2">
            <button class="w-full bg-white border border-gray-200 rounded-md py-1.5 px-3 text-gray-600 font-medium text-left shadow-sm flex items-center gap-2 hover:bg-gray-50">
                <svg class="w-4 h-4" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 5v14M5 12h14"/></svg>
                New feedback
                <span class="ml-auto text-xs text-gray-400">N</span>
            </button>
        </div>

        <!-- Navigation -->
        <div class="flex-1 overflow-y-auto px-2 py-1 space-y-6">
            <!-- Main Links -->
            <div class="space-y-0.5">
                <div class="flex items-center gap-2 px-2 py-1 rounded-md bg-gray-200/50 text-gray-900 font-medium">
                    <svg class="w-4 h-4 text-gray-500" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M3 9l9-7 9 7v11a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2z"/><polyline points="9 22 9 12 15 12 15 22"/></svg>
                    Home
                </div>
                <div class="flex items-center gap-2 px-2 py-1 rounded-md text-gray-600 hover:bg-gray-100">
                    <svg class="w-4 h-4 text-gray-500" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
                    Inbox
                </div>
                <div class="flex items-center gap-2 px-2 py-1 rounded-md text-gray-600 hover:bg-gray-100">
                    <svg class="w-4 h-4 text-gray-500" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"/></svg>
                    Messages
                </div>
                <div class="flex items-center gap-2 px-2 py-1 rounded-md text-gray-600 hover:bg-gray-100">
                    <svg class="w-4 h-4 text-gray-500" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/><polyline points="14 2 14 8 20 8"/><line x1="16" y1="13" x2="8" y2="13"/><line x1="16" y1="17" x2="8" y2="17"/><polyline points="10 9 9 9 8 9"/></svg>
                    Docs
                </div>
                <div class="flex items-center gap-2 px-2 py-1 rounded-md text-gray-600 hover:bg-gray-100">
                    <svg class="w-4 h-4 text-gray-500" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"/></svg>
                    Calls
                </div>
            </div>

            <!-- Favorites -->
            <div>
                <div class="px-2 text-xs font-medium text-gray-400 mb-1">Favorites</div>
                <div class="space-y-0.5">
                    {#each favorites as fav}
                        <div class="flex items-center gap-2 px-2 py-1 rounded-md text-gray-600 hover:bg-gray-100">
                            {#if fav.icon === 'star'}
                                <svg class="w-3.5 h-3.5 text-yellow-500" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/></svg>
                            {:else if fav.icon === 'alert'}
                                <svg class="w-3.5 h-3.5 text-red-500" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><line x1="12" y1="8" x2="12" y2="12"/><line x1="12" y1="16" x2="12.01" y2="16"/></svg>
                            {:else}
                                <svg class="w-3.5 h-3.5 text-gray-400" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/></svg>
                            {/if}
                            <span class="truncate">{fav.name}</span>
                        </div>
                    {/each}
                </div>
            </div>

            <!-- Projects -->
            <div>
                <div class="px-2 text-xs font-medium text-gray-400 mb-1">Projects</div>
                <div class="space-y-0.5">
                    {#each channels as channel}
                        <div class="flex items-center gap-2 px-2 py-1 rounded-md text-gray-600 hover:bg-gray-100">
                            <span class="text-gray-400">#</span>
                            <span class="truncate">{channel.name}</span>
                        </div>
                    {/each}
                </div>
            </div>
        </div>
    </div>

    <!-- Main Content -->
    <div class="flex-1 flex flex-col bg-white min-w-0">
        <!-- Header -->
        <div class="px-8 py-6 pb-2">
            <h2 class="text-2xl font-bold text-gray-900 mb-4">Home</h2>
            <div class="flex items-center justify-between border-b border-gray-100 pb-0">
                <div class="flex gap-6">
                    <button class="pb-2 border-b-2 border-black font-medium text-gray-900">For me</button>
                    <button class="pb-2 border-b-2 border-transparent font-medium text-gray-500 hover:text-gray-700">Created</button>
                    <button class="pb-2 border-b-2 border-transparent font-medium text-gray-500 hover:text-gray-700">All</button>
                </div>
                <button class="text-gray-400 hover:text-gray-600 mb-2">
                    <svg class="w-5 h-5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><line x1="4" y1="21" x2="4" y2="14"/><line x1="4" y1="10" x2="4" y2="3"/><line x1="12" y1="21" x2="12" y2="12"/><line x1="12" y1="8" x2="12" y2="3"/><line x1="20" y1="21" x2="20" y2="16"/><line x1="20" y1="12" x2="20" y2="3"/><line x1="1" y1="14" x2="7" y2="14"/><line x1="9" y1="8" x2="15" y2="8"/><line x1="17" y1="16" x2="23" y2="16"/></svg>
                </button>
            </div>
        </div>

        <!-- Input -->
        <div class="px-8 py-4">
            <div class="flex gap-3 items-start">
                <div class="w-8 h-8 rounded-full bg-gray-200 flex-shrink-0"></div>
                <div class="flex-1 relative">
                    <input type="text" placeholder="Report a bug or leave feedback..." class="w-full bg-transparent text-gray-900 placeholder-gray-400 focus:outline-none py-1.5" />
                </div>
                <button class="px-3 py-1.5 bg-gray-100 text-gray-400 rounded-md text-xs font-medium">Submit</button>
            </div>
        </div>

        <!-- Feed -->
        <div class="flex-1 overflow-y-auto px-8 pb-8">
            <!-- Today -->
            <div class="mb-6">
                <h3 class="text-xs font-medium text-gray-400 mb-3">Today</h3>
                <div class="space-y-4">
                    {#each posts as post}
                        <div class="group flex gap-3 items-start">
                            <div class="w-8 h-8 rounded-md {post.iconBg} flex items-center justify-center text-white text-xs font-bold flex-shrink-0 mt-0.5 shadow-sm border border-black/5">
                                {#if post.icon === 'P'}
                                    <span class="font-serif italic">P</span>
                                {:else}
                                    {post.icon}
                                {/if}
                            </div>
                            <div class="flex-1 min-w-0">
                                <div class="flex items-baseline gap-2">
                                    <span class="font-medium text-gray-900 truncate">{post.title}</span>
                                </div>
                                <div class="flex items-center gap-1.5 text-gray-500 text-xs mt-0.5">
                                    <span class="font-medium text-gray-600">{post.author}:</span>
                                    <span class="truncate">{post.preview}</span>
                                </div>
                            </div>
                            <div class="flex items-center gap-2 flex-shrink-0">
                                <span class="text-[10px] font-medium px-1.5 py-0.5 rounded bg-gray-50 {post.tagColor} border border-gray-100">{post.tag}</span>
                            </div>
                        </div>
                    {/each}
                </div>
            </div>

            <!-- Yesterday -->
            <div>
                <h3 class="text-xs font-medium text-gray-400 mb-3">Yesterday</h3>
                <div class="space-y-4">
                    {#each yesterdayPosts as post}
                        <div class="group flex gap-3 items-start">
                             <div class="w-8 h-8 rounded-md {post.iconBg} flex items-center justify-center text-white text-xs font-bold flex-shrink-0 mt-0.5 shadow-sm border border-black/5">
                                {post.icon}
                            </div>
                            <div class="flex-1 min-w-0">
                                <div class="flex items-baseline gap-2">
                                    <span class="font-medium text-gray-900 truncate">{post.title}</span>
                                </div>
                                <div class="flex items-center gap-1.5 text-gray-500 text-xs mt-0.5">
                                    <span class="font-medium text-gray-600">{post.author}:</span>
                                    <span class="truncate">{post.preview}</span>
                                </div>
                            </div>
                            <div class="flex items-center gap-2 flex-shrink-0">
                                <span class="text-[10px] font-medium px-1.5 py-0.5 rounded bg-gray-50 {post.tagColor} border border-gray-100">{post.tag}</span>
                            </div>
                        </div>
                    {/each}
                </div>
            </div>
        </div>
    </div>

    <!-- Right Sidebar -->
    <div class="w-64 border-l border-gray-200 bg-gray-50 flex flex-col flex-shrink-0">
        <div class="p-3">
             <div class="relative">
                <svg class="absolute left-2.5 top-2 w-4 h-4 text-gray-400" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="11" cy="11" r="8"/><line x1="21" y1="21" x2="16.65" y2="16.65"/></svg>
                <input type="text" placeholder="Search people..." class="w-full bg-white border border-gray-200 rounded-md pl-9 pr-3 py-1.5 text-sm placeholder-gray-400 focus:outline-none focus:border-gray-300" />
            </div>
        </div>

        <div class="flex-1 overflow-y-auto px-3 py-2">
            <div class="flex items-center gap-1.5 text-xs text-gray-400 font-medium mb-3">
                <div class="w-1.5 h-1.5 rounded-full bg-green-500"></div>
                4 online
            </div>
            
            <div class="space-y-3">
                {#each team as member}
                    <div class="flex items-start gap-2">
                        <div class="relative">
                            <img src={member.img} alt={member.name} class="w-8 h-8 rounded-full bg-gray-200" />
                            {#if member.online}
                                <div class="absolute -bottom-0.5 -right-0.5 w-2.5 h-2.5 bg-green-500 border-2 border-gray-50 rounded-full"></div>
                            {/if}
                        </div>
                        <div class="flex-1 min-w-0">
                            <div class="text-sm font-medium text-gray-900 truncate">{member.name}</div>
                            {#if member.status}
                                <div class="text-xs text-gray-500 truncate flex items-center gap-1">
                                    {#if member.status === 'Focus'}
                                        <span>🧘</span>
                                    {/if}
                                    {member.status}
                                </div>
                            {/if}
                        </div>
                    </div>
                {/each}
            </div>

             <div class="mt-6">
                <div class="flex items-center gap-1.5 text-xs text-gray-400 font-medium mb-3">
                    <svg class="w-3 h-3" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"/><circle cx="9" cy="7" r="4"/><path d="M23 21v-2a4 4 0 0 0-3-3.87"/><path d="M16 3.13a4 4 0 0 1 0 7.75"/></svg>
                    Guests
                </div>
            </div>
        </div>
    </div>
</div>
