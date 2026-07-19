var app = angular.module("certApp", ["ngRoute"]);

app.config(function($routeProvider){
    $routeProvider
    .when("/home", { templateUrl:"views/home.html", controller:"HomeCtrl" })
    .when("/certifications", { templateUrl:"views/certifications.html", controller:"CertCtrl" })
    .when("/subscriptions", { templateUrl:"views/subscriptions.html", controller:"SubCtrl" })
    .when("/dashboard", { templateUrl:"views/dashboard.html", controller:"DashboardCtrl" })
    .when("/exam", { templateUrl:"views/exam.html", controller:"ExamCtrl" })
    .when("/contact", { templateUrl:"views/contact.html", controller:"ContactCtrl" })
    .when("/login", { templateUrl:"views/login.html", controller:"LoginCtrl" })
    .otherwise({ redirectTo:"/home" });
});


app.run(function($rootScope){
    $rootScope.user = null;
    $rootScope.preselectedCourseId = null; // Coordinates route navigation direct entry targets
});

app.controller("HomeCtrl", function($scope){
    $scope.features=[
        { icon:"bi-terminal", title:"3 Distinct Framework Curriculums", desc:"Deep processing paths analyzing structural variables from basics up to core memory footprint optimizations." },
        { icon:"bi-collection-play", title:"Automated Mock Sandboxes", desc:"Generates exactly 10 comprehensive testing criteria matching selected course pathways dynamically." },
        { icon:"bi-shield-check", title:"Cryptographic Credential Badges", desc:"Fully verifiable identity tokens map safely to talent indexing tracking structures." }
    ];
});

app.controller("CertCtrl", function($scope, $rootScope, $location){
    $scope.certifications=[
        { id:"associate", name:"Angular Associate Course", level:"Fundamentals Validation Matrix", details:"Focuses heavily on two-way scope bindings, declarative built-in structural directives, custom data filters execution, and foundational standard layouts rendering parameters." },
        { id:"professional", name:"Angular Professional Course", level:"Advanced Dynamic Operations", details:"Focuses on modular processing partitions configuration, asynchronous HTTP pipeline operational interceptors, component routing security protections, and state resolution guards." },
        { id:"architect", name:"Angular Architect Course", level:"Enterprise Scale Engineering Optimization", details:"Focuses on strategic performance overhead suppression, automated change calculation profiling, compiler level injection adjustments, and custom framework extending schemas." }
    ];

    $scope.selectAndGoToExam = function(courseId){
        $rootScope.preselectedCourseId = courseId;
        $location.path("/exam");
    };
});

app.controller("SubCtrl", function($scope){
    $scope.pricingPlans = [
        { title: "Standard Track", cost: "299", term: "mo", perks: ["Access to basic associate structures", "Continuous testing evaluation loops", "Standard ticket response channel Access"], isPopular: false },
        { title: "Developer Pro Pass", cost: "899", term: "mo", perks: ["Unlock all 3 specialized high-scale courses", "Generate unlimited 10-question sandbox modules", "Includes 1 certification validation exam verification token"], isPopular: true },
        { title: "Enterprise Fleet Pass", cost: "1299", term: "yr", perks: ["Full yearly access mapping tracking systems", "Direct offline repository cloning configurations", "Priority real-time operational response support logs"], isPopular: false }
    ];
    $scope.buyTier = function(n){ alert("Subscription processing path launched for profile: " + n); };
});

app.controller("DashboardCtrl", function($scope){
    $scope.student={
        name: "Developer Candidate Alpha",
        progress: 70,
        completed: ["Core Directive Scopes Architecture Setup", "Template Variable Interlinings", "SPA Viewport Component Routers Integration Models"]
    };
});

app.controller("ExamCtrl", function($scope, $rootScope, $interval){
    $scope.examStarted = false;
    $scope.examSubmitted = false;
    $scope.showCertificate = false;
    $scope.currentDate = new Date();
    $scope.timer = 180;
    $scope.score = 0;
    $scope.selectedAnswers = {};

    $scope.courseTracks = [
        { id: "associate", name: "Angular Associate Fundamentals", summary: "Tests standard template expressions bindings, directives syntaxes, and scopes management structures." },
        { id: "professional", name: "Angular Professional Applications", summary: "Tests modular dynamic architectures, custom routing guards, and systemic HTTP pipeline interceptors." },
        { id: "architect", name: "Angular Enterprise System Architect", summary: "Tests compilation lifecycles, memory leak reduction, and change-detection tuning configurations." }
    ];

    $scope.selectedTrack = $scope.courseTracks[0];

    if($rootScope.preselectedCourseId){
        var matchingTrack = $scope.courseTracks.find(function(t){ return t.id === $rootScope.preselectedCourseId; });
        if(matchingTrack){ $scope.selectedTrack = matchingTrack; }
        $rootScope.preselectedCourseId = null;
    }

    var questionRepository = {
        associate: [
            { type: "multiple-choice", prompt: "1. Which prefix directive string is used to append standard framework entities directly to standard elements?", choices: ["ag-", "ng-", "aj-", "dx-"], solution: "ng-" },
            { type: "multiple-choice", prompt: "2. What is the standard configuration symbol wrapping syntax used to output interpolation expressions safely to views?", choices: ["(expression)", "[expression]", "{{expression}}", "${expression}"], solution: "{{expression}}" },
            { type: "multiple-choice", prompt: "3. Which operational core directive binds structural input control target parameters to component data model contexts?", choices: ["ng-bind", "ng-controller", "ng-model", "ng-init"], solution: "ng-model" },
            { type: "multiple-choice", prompt: "4. How many $rootScope instances can be initialized concurrently within a standard single app domain instance space?", choices: ["Exactly One", "Two", "Unlimited", "Zero"], solution: "Exactly One" },
            { type: "multiple-choice", prompt: "5. Which directive enables conditional inclusion or template stripping removal directly from the DOM tree structure?", choices: ["ng-show", "ng-if", "ng-hide", "ng-style"], solution: "ng-if" },
            { type: "multiple-choice", prompt: "6. Which specialized filter utility translates standard string layouts into lower-case formatting matches automatically?", choices: ["textDown", "lowercase", "lower", "formatMin"], solution: "lowercase" },
            { type: "multiple-choice", prompt: "7. Which core directive initializes the application shell context execution grid boundary over a DOM branch?", choices: ["ng-app", "ng-init", "ng-bootstrap", "ng-start"], solution: "ng-app" },
            { type: "multiple-choice", prompt: "8. What framework model component contains the operational programmatic state logic instructions governing targeted views?", choices: ["Filter", "Directive", "Service", "Controller"], solution: "Controller" },
            { type: "text-formula", prompt: "9. Identify the core directive keyword configuration attribute used to populate loop element clones over an iterative array stack: (Input exact attribute naming string)", solution: "ng-repeat" },
            { type: "text-formula", prompt: "10. Identify the target core directive identifier syntax used to output plain model data strings directly as element innerText without bracket interpolations:", solution: "ng-bind" }
        ],
        professional: [
            { type: "multiple-choice", prompt: "1. Which configuration provider manages the global addition of preprocessing filter transformations onto execution tracking chains?", choices: ["$httpProvider.interceptors", "$routeProvider.when", "$locationProvider", "$compileProvider"], solution: "$httpProvider.interceptors" },
            { type: "multiple-choice", prompt: "2. What methodology allows structural single-page modular sections to defer payload downloads until explicitly required by route changes?", choices: ["Eager Injection", "Lazy Loading", "Dynamic Interpolation", "Digest Debouncing"], solution: "Lazy Loading" },
            { type: "multiple-choice", prompt: "3. Which parameter method manually forces evaluation sweeps across data scopes tracking asynchronous event completions?", choices: ["$scope.$apply()", "$scope.$watch()", "$scope.$observe()", "$scope.$eval()"], solution: "$scope.$apply()" },
            { type: "multiple-choice", prompt: "4. What is the explicit method signature pattern utilized to map catch-all redirect handlers into the application routing configurations table?", choices: ["otherwise()", "fallback()", "redirectTo()", "redirect()"], solution: "otherwise()" },
            { type: "multiple-choice", prompt: "5. Which flag property identifies that form values have been explicitly modified from their starting default settings?", choices: ["$invalid", "$pristine", "$dirty", "$touched"], solution: "$dirty" },
            { type: "multiple-choice", prompt: "6. What structural mechanism intercepts view execution matching to prevent unauthenticated access navigation vectors?", choices: ["Route Guards", "Dynamic Filters", "$http Interceptors", "Digest Compilers"], solution: "Route Guards" },
            { type: "multiple-choice", prompt: "7. Which builtin abstraction manages HTML5 history mode state manipulation across address browser bar contexts smoothly?", choices: ["$anchorScroll", "$window", "$location", "$document"], solution: "$location" },
            { type: "multiple-choice", prompt: "8. What is the architectural behavior of an AngularJS custom Service component lifecycle pattern?", choices: ["Transient instance per execution", "Immutable Factory method", "Singleton state instance object", "Static metadata array"], solution: "Singleton state instance object" },
            { type: "text-formula", prompt: "9. Identify the specialized target method keyword configuration name string utilized to construct distinct functional modules across app boundaries:", solution: "angular.module" },
            { type: "text-formula", prompt: "10. Identify the dynamic framework configuration block parameter string where providers can have their execution properties customized before runtime startup takes place:", solution: "config" }
        ],
        architect: [
            { type: "multiple-choice", prompt: "1. What internal calculation cycle loop updates component views by iteratively scanning bound tracking scopes variables for delta offsets?", choices: ["Compilation Phase", "Digest Cycle", "Injection Strategy", "Scythe Routine"], solution: "Digest Cycle" },
            { type: "multiple-choice", prompt: "2. Which structural methodology minimizes application memory overhead optimization footprints when executing enormous loop items lists?", choices: ["Scope nesting duplication", "One-way data binding standard optimizations", "$rootScope redirection models", "Synchronous HTTP parsing closures"], solution: "One-way data binding standard optimizations" },
            { type: "multiple-choice", prompt: "3. What process compiles standard text templates configurations directly into functional executable rendering link formulas at boot times?", choices: ["$compile service transformations", "$parse execution blocks", "$interpolate calculations", "$animate transitions"], solution: "$compile service transformations" },
            { type: "multiple-choice", prompt: "4. Which structural optimization flag should be set to disabled in production mode environments to avoid heavy DOM structural metadata element tracking extensions overheads?", choices: ["strictDI", "debugInfoEnabled", "html5Mode", "lazyLoad"], solution: "debugInfoEnabled" },
            { type: "multiple-choice", prompt: "5. What design problem arises if sub-scopes initialize variables that accidentally overlap parent scope primitive property key tracking naming systems?", choices: ["Scope Shadowing Mutation Errors", "Dependency Injection collisions", "Digest loops structural overflow exception", "Directive controller context dropouts"], solution: "Scope Shadowing Mutation Errors" },
            { type: "multiple-choice", prompt: "6. Which parameter execution option enforces explicit structural dependency annotations matching configurations to ensure compression safety during build minification steps?", choices: ["ng-strict-di", "ng-app", "ng-cloak", "ng-hint"], solution: "ng-strict-di" },
            { type: "multiple-choice", prompt: "7. What specific structural design pattern implements separation of concerns inside application injection pipelines?", choices: ["Dependency Injection", "Singleton Module Pipeline Strategy", "Active Observer Pipeline", "Decorated Template Engine Model"], solution: "Dependency Injection" },
            { type: "multiple-choice", prompt: "8. Which methodology tracks runtime operations metrics cleanly without creating permanent trace leaks inside disconnected scope structures?", choices: ["$destroy state cleanup lifecycle events monitoring", "$apply tracking loop extensions", "$watch collection evaluations profiling", "$rootScope global broadcast listeners cascades"], solution: "$destroy state cleanup lifecycle events monitoring" },
            { type: "text-formula", prompt: "9. Identify the specific scope tracking method name string utilized to watch complex inner property mutation hierarchies deep within child object structures: (Do not append method brackets)", solution: "$watch" },
            { type: "text-formula", prompt: "10. Identify the native AngularJS bootstrap initialization method framework function string used to kick off software execution manually over custom structural elements:", solution: "angular.bootstrap" }
        ]
    };

    $scope.chooseTrack = function(track){
        if(!$scope.examStarted){ $scope.selectedTrack = track; }
    };

    $scope.generateAndStartTest = function(){
        $scope.activeQuestionSet = angular.copy(questionRepository[$scope.selectedTrack.id]);
        $scope.selectedAnswers = {};
        $scope.examSubmitted = false;
        $scope.showCertificate = false;
        $scope.score = 0;
        $scope.timer = 180;
        $scope.examStarted = true;

        $scope.stopTicker(); 
        $scope.countdownTimerToken = $interval(function(){
            if($scope.timer > 0 && !$scope.examSubmitted){
                $scope.timer--;
            } else if($scope.timer === 0 && !$scope.examSubmitted) {
                $scope.processGradingRoutine();
            }
        }, 1000);
    };

    $scope.isAnswerCorrect = function(index, qItem){
        var candidateInput = $scope.selectedAnswers[index];
        if(!candidateInput) return false;

        if(qItem.type === 'text-formula'){
            return candidateInput.trim().toLowerCase() === qItem.solution.trim().toLowerCase();
        }
        return candidateInput === qItem.solution;
    };

    $scope.processGradingRoutine = function(){
        $scope.examSubmitted = true;
        $scope.stopTicker();
        $scope.score = 0;

        angular.forEach($scope.activeQuestionSet, function(q, idx){
            if($scope.isAnswerCorrect(idx, q)){
                $scope.score++;
            }
        });
    };
    
    $scope.generateCertificate = function(){
        $scope.showCertificate = true;
    };
    $scope.closeCertificate = function(){
        $scope.showCertificate = false;
    };

    $scope.resetSandboxEnvironment = function(){
        $scope.examStarted = false;
        $scope.examSubmitted = false;
        $scope.showCertificate = false;
        $scope.selectedAnswers = {};
        $scope.score = 0;
    };

    $scope.stopTicker = function() {
        if (angular.isDefined($scope.countdownTimerToken)) {
            $interval.cancel($scope.countdownTimerToken);
            $scope.countdownTimerToken = undefined;
        }
    };

    $scope.$on('$destroy', function() { $scope.stopTicker(); });
});

app.controller("ContactCtrl", function($scope){
    $scope.ticket = { name: "", email: "", msg: "" };
    $scope.sendTicket = function(form){
        if(form.$valid){
            alert("Support Ticket generation successful! Log trace created: TKT-" + Math.floor(Math.random() * 80000 + 20000));
            $scope.ticket = { name: "", email: "", msg: "" };
            form.$setPristine();
            form.$setUntouched();
        }
    };
});

app.controller("LoginCtrl", function($scope, $rootScope, $location){
    $scope.loginData = { email: "", password: "" };
    $scope.validationError = null;

    $scope.hasUppercase = function(str) { return /[A-Z]/.test(str || ''); };
    $scope.hasLowercase = function(str) { return /[a-z]/.test(str || ''); };
    $scope.hasSpecialChar = function(str) { return /[@$!%*?&]/.test(str || ''); };

    $scope.login = function(){
        $scope.validationError = null;
        var pass = $scope.loginData.password || "";

        if (pass.length < 8) { $scope.validationError = "Password must contain at least 8 elements."; return; }
        if (!$scope.hasUppercase(pass)) { $scope.validationError = "Password missing uppercase elements [A-Z]."; return; }
        if (!$scope.hasLowercase(pass)) { $scope.validationError = "Password missing lowercase elements [a-z]."; return; }
        if (!$scope.hasSpecialChar(pass)) { $scope.validationError = "Password missing a special tracking symbol characters."; return; }

        $rootScope.user = $scope.loginData.email;
        alert("Gate security checks validated successfully!");
        $location.path("/dashboard"); 
    };
});
