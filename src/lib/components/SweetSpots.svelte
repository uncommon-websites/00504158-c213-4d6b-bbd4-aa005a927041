<section class="py-24 px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto flex flex-col items-center">
    <h2 class="text-3xl sm:text-4xl font-bold text-center text-gray-900 mb-12 max-w-xl tracking-tight">
        Point, click, annotate.<br />
        Feedback in seconds.
    </h2>

    <div class="relative w-full max-w-2xl">
        <!-- Mock Feedback Card -->
        <div class="bg-white rounded-xl shadow-sm border border-gray-200 p-4 flex items-start gap-4">
            <div class="w-10 h-10 rounded-full bg-red-100 flex items-center justify-center flex-shrink-0">
                <svg class="w-5 h-5 text-red-600" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <circle cx="12" cy="12" r="10"/>
                    <line x1="12" y1="8" x2="12" y2="12"/>
                    <line x1="12" y1="16" x2="12.01" y2="16"/>
                </svg>
            </div>
            <div class="flex-1 min-w-0">
                <div class="flex items-center gap-2 mb-1">
                    <span class="font-semibold text-gray-900">Button alignment off on mobile</span>
                    <span class="inline-flex items-center gap-1 px-2 py-0.5 rounded-full bg-red-50 border border-red-200 text-xs font-medium text-red-700">
                        High Priority
                    </span>
                </div>
                <div class="flex items-center gap-2 text-sm text-gray-500 mb-2">
                    <span class="font-medium text-gray-900">Sarah Chen</span>
                    <span>•</span>
                    <span>2 minutes ago</span>
                </div>
                <p class="text-sm text-gray-600 mb-2">The CTA button is misaligned by 3px on iPhone 14. Should be centered with the hero text.</p>
                <div class="flex items-center gap-2">
                    <span class="inline-flex items-center gap-1 px-2 py-1 rounded bg-gray-100 text-xs font-medium text-gray-600">
                        <svg class="w-3 h-3" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"/><polyline points="7 10 12 15 17 10"/><line x1="12" y1="15" x2="12" y2="3"/></svg>
                        screenshot.png
                    </span>
                    <span class="text-xs text-gray-400">iPhone 14 Pro • Safari</span>
                </div>
            </div>
        </div>

        <!-- Hand drawn arrow and text -->
        <div class="absolute -bottom-16 left-1/2 -translate-x-1/2 flex flex-col items-center">
             <div class="relative">
                <svg width="120" height="60" viewBox="0 0 120 60" fill="none" class="text-gray-300 transform rotate-12">
                    <path d="M10,50 Q60,60 110,10" stroke="currentColor" stroke-width="2" fill="none" marker-end="url(#arrowhead)" />
                    <defs>
                        <marker id="arrowhead" markerWidth="10" markerHeight="7" refX="10" refY="3.5" orient="auto">
                        <polygon points="0 0, 10 3.5, 0 7" fill="currentColor" />
                        </marker>
                    </defs>
                </svg>
                <span class="absolute top-8 left-1/2 -translate-x-1/2 text-gray-400 font-handwriting text-sm whitespace-nowrap font-serif italic">Real feedback</span>
            </div>
        </div>
    </div>
</section>
