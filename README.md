# yun
ios app引导页
// 设置APP引导页
    if (![[NSUserDefaults standardUserDefaults] boolForKey:BOOLFORKEY]) {
        [[NSUserDefaults standardUserDefaults] setBool:YES forKey:BOOLFORKEY];
       
        [self setStaticGuidePage]; // 静态引导页
    
        //[self setDynamicGuidePage];// 动态引导页
    
        //[self setVideoGuidePage];// 视频引导页
    }
    
#pragma mark - 设置APP静态图片引导页
- (void)setStaticGuidePage {
    NSArray *imageNameArray = @[@"guideImage1.jpg",@"guideImage2.jpg",@"guideImage3.jpg",@"guideImage4.jpg",@"guideImage5.jpg"];
    DHGuidePageHUD *guidePage = [[DHGuidePageHUD alloc] dh_initWithFrame:self.view.frame imageNameArray:imageNameArray buttonIsHidden:NO];
    guidePage.slideInto = YES;
    [self.navigationController.view addSubview:guidePage];
}

#pragma mark - 设置APP动态图片引导页
- (void)setDynamicGuidePage {
    NSArray *imageNameArray = @[@"guideImage6.gif",@"guideImage7.gif",@"guideImage8.gif"];
    DHGuidePageHUD *guidePage = [[DHGuidePageHUD alloc] dh_initWithFrame:self.view.frame imageNameArray:imageNameArray buttonIsHidden:YES];
    guidePage.slideInto = YES;
    [self.navigationController.view addSubview:guidePage];
}

#pragma mark - 设置APP视频引导页
- (void)setVideoGuidePage {
    NSURL *videoURL = [NSURL fileURLWithPath:[[NSBundle mainBundle] pathForResource:@"guideMovie1" ofType:@"mov"]];
    DHGuidePageHUD *guidePage = [[DHGuidePageHUD alloc] dh_initWithFrame:self.view.bounds videoURL:videoURL];
    [self.navigationController.view addSubview:guidePage];
}
