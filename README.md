*Thinking...*

>  I need to put together a comprehensive training deck for the IT Cloud Team covering the progression from large language models to agentic AI solutions, along with practical implementation using VSCode, Azure infrastructure, OpenTofu, and building a custom Copilot plugin with MCP configuration, skills, and agents.
> 
> I'm considering whether to search for the latest information on Model Context Protocol, GitHub Copilot extensions, and agentic frameworks since there's been rapid evolution in this space and my knowledge has a gap to the current date. The specific terminology around skills, agents, hooks, and instructions suggests I should verify the current state of Copilot's capabilities and MCP specifications to ensure the training deck reflects what's actually available now.
> 
>  I've got a solid foundation on Copilot customization and MCP architecture, so now I'm digging into the specific technical details—how to set up VSCode for Azure infrastructure with OpenTofu plugins, and how to build a Copilot extension. Let me run a few searches in parallel to fill in those gaps.
> 
>  I'm organizing the training deck structure to cover the evolution from LLMs to agentic solutions, then walking through a complete VSCode setup with cloud infrastructure tools, and finally building out a Copilot plugin with all the necessary components like MCP configuration, skills, agents, hooks, and instructions. Building the slide deck component... Setting up the OpenTofu configuration with Azure provider, remote state backend, and resource group creation, then defining MCP server configurations for GitHub, Azure, and Terraform integrations in VS Code, along with a plugin manifest structure. Finishing the module scaffold steps with version pinning and validation, then setting up the custom IaC planner agent that analyzes Azure architecture requirements and hands off to an implementer, along with hooks to enforce OpenTofu formatting and block unsafe apply operations.
> 
> Now I'm thinking through the evolution from basic LLMs to agentic systems—starting with token prediction, adding retrieval for knowledge, then tool use for actions, MCP for standardized connections, and finally autonomous agents that can plan multi-step workflows, make decisions about which tools to use, and adapt based on feedback. I'll structure this as a clear progression showing how each layer builds on the previous one.
> 
> Building a React slide deck component... I'm mapping out the full deck structure now—starting with foundations on LLMs and the evolution toward agentic systems, then moving into the practical environment setup with VSCode, Azure, and OpenTofu, and finally the Copilot plugin architecture with all its customization layers like instructions, skills, agents, and hooks.
> 
> Now I'm planning the visual design with a dark slate background and cyan/blue/purple accents, where each slide displays a section label, title, and content. I'll create helper components for code blocks, pills, and cards, then build a responsive deck container with a header showing progress, a main slide area, and footer navigation controls.
> 
> Building the slide rendering system... Building the presentation component... Writing the component... I need to escape template literal interpolations like `${file}` and `${input:...}` by writing them as `\${file}` and `\${input:...}` to prevent JavaScript from trying to evaluate them. I'll also keep the JSON and HCL samples simple—avoiding backticks and dollar-sign interpolations where possible, or escaping them carefully when they're necessary. Writing component styles... Defining accent color mappings...
> 
> Now I'm planning the slide content structure. I'll create an evolution ladder showing how LLMs progress through RAG, tools, MCP, and into agent modes, then move to slides covering the three pillars of agentic behavior—independence, decision-making, and adaptation. I'll also need slides explaining the MCP USB-C analogy, what it standardizes with its primitives and transports, and the architecture showing how hosts, clients, and servers interact via JSON-RPC.
> 
> Next I'm laying out the customization layers—six building blocks as cards covering instructions, prompt files, custom agents, skills, MCP servers, and hooks. I'll add a decision matrix to guide when to use each layer, then show the plugin anatomy with a directory tree and plugin.json structure.
> 
> Rendering the directory tree...
> 
> Then I'll walk through how a single user prompt flows through the system: someone asks to stand up a new AKS landing zone, instructions inject standards, the planner agent reads from Azure and Terraform MCPs, hands off to the implementer agent which scaffolds via a skill, hooks enforce policy before apply, and finally a GitHub MCP creates the PR.
> 
> For the security and governance slide, I'm covering MCP trust models—only trusted sources, org policy controls with defaults disabled for enterprise, VS Code's rug-pull protection resetting permissions on tool changes, secrets via Key Vault inputs never hardcoded, push protection blocking leaks, and least privilege tool assignment per agent.
> 
> The roadmap is phased: standardize the VS Code workspace, add MCP servers, author instructions, build skills and agents, package as a plugin for marketplace distribution, then add hooks and governance.
> 
> Now I'm writing the code carefully with reusable layout helpers to keep slides consistent.
> 
> Building the component with Framer Motion for slide transitions using fade and slide animations with AnimatePresence, handling arrow key navigation for left/right while allowing vertical scroll, and making everything responsive with mobile-first breakpoints. The header shows a section indicator and slide counter with a progress bar, the footer has prev/next buttons and section tabs for jumping between the five main sections.
> 
> I'm setting up the Terraform code to show the azurerm provider with the correct opentofu source and version constraints, including the main.tf with the terraform block for required_providers and backend configuration, then adding a sample resource. I'll also add a footer note about the mid-2026 tooling context.
> 
> Now I'm framing the final answer with citations covering MCP as an open standard connecting LLMs to tools, the architecture details around host/client/server and JSON-RPC, and Copilot's agentic capabilities, then presenting the React component artifact followed by a closing note offering to adapt the deck further. Writing the presentation slides... I need to put together a comprehensive training presentation for an IT Cloud Team covering AI evolution from large language models through to agentic solutions. This involves structuring content around AI fundamentals and the progression to more autonomous systems, then building out practical components like a fully configured VSCode environment with cloud infrastructure tools, and finally creating a custom Copilot plugin with all the necessary configuration including model context protocol setup, skill definitions, agent configurations, and system instructions.
> 
> I should consider whether I need to search for the latest developments since some of these technologies like GitHub Copilot's agentic features and MCP integrations have been evolving rapidly, and my knowledge extends to May 2025 while we're now in June 2026. However, I can create a solid foundational training deck based on my existing knowledge and note where the team might want to incorporate the most current tooling updates.
> 
>  I've got solid coverage on GitHub Copilot's agent mode with MCP, customization options like instructions and custom agents, plus OpenTofu and VSCode setup. I should do a couple more targeted searches to fill in gaps around how Copilot's plugin system works as a packaging mechanism and get more details on the Azure infrastructure side for VSCode.
> 
>  I'm pulling together what I've learned about how LLMs evolved into agentic systems—from code completion through chat interfaces to autonomous multi-step agents—and how MCP support enabled these capabilities. Now I'm thinking through the practical setup needed, starting with VSCode infrastructure like the OpenTofu extension.
> 
> I'm also mapping out the customization primitives available in Copilot: instructions that run continuously, manually-invoked prompts, auto-discovered skills, custom agents with their own personas and tools, deterministic hooks tied to lifecycle events, MCP servers for live external data, and plugins as the packaging mechanism. The configuration lives in files like .vscode/mcp.json for server connections and plugin.json for plugin metadata, with agents and skills organized in a structured directory layout. Hooks tie into eight different lifecycle events throughout the session and tool execution flow.
> 
> Now the user wants me to build a training deck for presentation to their IT Cloud Team, so I'm planning a React-based interactive slide deck with navigation controls, multiple sections covering the evolution from LLMs to agentic solutions, and clean professional styling suitable for technical audiences.
> 
> Building the slide deck component... Building the React component now... Wrapping up the remaining slides through the closing, then planning the implementation: I'll structure the deck as an array of slide components with keyboard navigation via useEffect. For the code blocks, I'm keeping them simple with monospace text and a filename header bar rather than attempting syntax highlighting. I'll pull in icons from lucide-react to visually break up sections.
> 
> For layout, I'm using a full-screen dark container with a centered slide card that scrolls if needed, plus a progress bar at the bottom and section tracking in the header. I'll create small helper components like SlideShell, CodeBlock, and Card to keep the code organized and maintainable.
> 
> Now writing out the slide content itself... I'm settling on a React component with about 28 slides organized by section, using a slides array with inline JSX bodies to keep it maintainable while covering the full scope from LLM fundamentals through agentic systems, MCP architecture, and VS Code tooling.
> 
> Now I'm defining the design system — a dark slate background with cyan-to-blue accent gradients, plus emerald for agentic concepts, violet for MCP, and amber for hooks to create visual distinction across sections.
> 
> I'm building helper components for the presentation: a CodeBlock that displays file snippets with syntax highlighting and proper formatting, a Pill component for badges, and a Card for bordered containers. The main layout uses a flex column structure with a header, scrollable slide content area, and footer controls with progress tracking.
> 
> For navigation and transitions, I'll wire up keyboard controls for arrow keys and space to move between slides, and use Framer Motion's AnimatePresence to create smooth fade and slide animations as the presentation advances.
> 
> I need to stick with standard Tailwind classes like w-3.5, h-3.5, text-xs, and max-w-5xl to avoid arbitrary values. For the visual diagrams—the ladder and agentic loop—I'll use flex rows with cards connected by chevron icons to show the progression and feedback loops.
> 
> Now I'm structuring the slides as a constant array where each entry contains a section, title, and body with JSX content. I'll define all the helper components first since they're hoisted, then the SLIDES array, then the main App component.
> 
> For the content itself, I'm mapping out the key messages: LLMs are pattern-matching systems with inherent limitations around knowledge cutoff and lack of agency, so they need tools and context to be operationally useful. Agentic systems add planning, tool use, observation, and adaptation in a loop. MCP is the open standard that solves the integration problem—it's JSON-RPC 2.0 based, governed by the Linux Foundation now, and supports both local and remote transports with OAuth for security.
> 
> Now I'm structuring the plugin configuration with a plugin.json manifest that declares the agent, skills, hooks, and MCP servers, then defining the .mcp.json file to wire up the actual servers—GitHub via HTTP, Azure via the official MCP server package, and Terraform similarly. I need to be careful to use real, plausible server identifiers rather than made-up ones. I'll keep the config simple and generic with a note to swap in the actual provider's MCP server. For the concrete examples, I'm using GitHub and Azure, then adding Terraform as another option. Now I'm looking at the skill definition for OpenTofu module review, which outlines validation steps like format checking and provider version verification. The agent manifest describes an IaC planner that uses Claude Opus and can hand off to an implementer, with access to codebase search and Terraform tools. Finally, I'm setting up the hooks configuration with pre and post tool-use commands that run guard scripts for infrastructure changes.
> 
> Now I'm documenting the instruction files and marketplace setup — scoped instructions for Terraform files that enforce provider pinning and secret management via Key Vault. With that foundation in place, I'm moving into building the React presentation component. I'll structure it with a consistent shell that handles the slide title, then render body content below. I'm creating a helper component for bullet points with icons to keep the list styling uniform throughout the deck. For the main component, I need to handle responsive design so it works on mobile — text scales appropriately and code blocks scroll horizontally. I'm importing Framer Motion for animations and setting up navigation buttons with proper disabled states.
> 
> Writing the component now...
> 
> For navigation and usability, I'm adding section tabs at the top that jump to the first slide of each section, with a progress indicator showing the current position. I'm mapping section names to accent colors — Evolution gets cyan, MCP gets violet, Environment gets emerald, Agent Mode gets blue, Build a Plugin gets amber, and Wrap-up gets rose. This creates visual consistency while distinguishing each major topic.
> 
> Writing theme mapping...

I'll research the latest developments on these fast-moving topics before building your training deck, since GitHub Copilot's agentic features, MCP support, and tooling have been evolving rapidly.Let me get details on the Copilot plugin packaging format and Azure infrastructure tooling for VSCode to round out the technical content.




*Thinking...*

>  Now I'm mapping out the detailed adoption roadmap for each phase of the React training deck, building on the foundation of standardizing the workspace, integrating MCP servers, encoding IaC standards, and establishing the agent team structure.
> 
> I'm creating an interactive React component that expands each of the six phases with objectives, tasks, deliverables, owners, duration, success criteria, and risks — making it a comprehensive visual roadmap that teams can follow step-by-step through their adoption journey. I'm thinking about how to present this roadmap in an interactive way—making each phase expandable so users can click through and see the details without overwhelming them all at once.

I'll expand that roadmap slide into a detailed, interactive component your team can actually work from — each phase with objectives, a concrete task checklist, deliverables, owners, duration, exit criteria, and key risks. Click any phase to expand it.

```jsx type=react
import React, { useState } from 'react';
import { motion, AnimatePresence } from 'framer-motion';
import {
  Terminal, Plug, BookOpen, Bot, ShieldCheck, Package,
  ChevronDown, Target, ListChecks, FileOutput, Users, Clock,
  Flag, AlertTriangle, CheckCircle2, Layers
} from 'lucide-react';

/* ----------------------------- Theme ----------------------------- */
const ACCENTS = {
  emerald: { text: 'text-emerald-300', bg: 'bg-emerald-500/10', dot: 'bg-emerald-400', border: 'border-emerald-400/30', ring: 'ring-emerald-400/30', grad: 'from-emerald-500 to-teal-500' },
  violet:  { text: 'text-violet-300',  bg: 'bg-violet-500/10',  dot: 'bg-violet-400',  border: 'border-violet-400/30',  ring: 'ring-violet-400/30',  grad: 'from-violet-500 to-purple-500' },
  cyan:    { text: 'text-cyan-300',    bg: 'bg-cyan-500/10',    dot: 'bg-cyan-400',    border: 'border-cyan-400/30',    ring: 'ring-cyan-400/30',    grad: 'from-cyan-500 to-sky-500' },
  blue:    { text: 'text-blue-300',    bg: 'bg-blue-500/10',    dot: 'bg-blue-400',    border: 'border-blue-400/30',    ring: 'ring-blue-400/30',    grad: 'from-blue-500 to-indigo-500' },
  amber:   { text: 'text-amber-300',   bg: 'bg-amber-500/10',   dot: 'bg-amber-400',   border: 'border-amber-400/30',   ring: 'ring-amber-400/30',   grad: 'from-amber-500 to-orange-500' },
  rose:    { text: 'text-rose-300',    bg: 'bg-rose-500/10',    dot: 'bg-rose-400',    border: 'border-rose-400/30',    ring: 'ring-rose-400/30',    grad: 'from-rose-500 to-pink-500' },
};

/* ----------------------------- Data ----------------------------- */
const PHASES = [
  {
    id: 1,
    icon: Terminal,
    accent: 'emerald',
    title: 'Standardize the Workspace',
    tagline: 'A reproducible toolchain every engineer can spin up in under an hour.',
    duration: '~2 weeks',
    owners: 'Platform lead + 1 engineer',
    objective:
      'Eliminate "works on my machine" by codifying the entire local dev environment — editor, extensions, CLIs, and a dev container — so onboarding is a single command.',
    tasks: [
      'Pin the VSCode extension set: GitHub Copilot, Copilot Chat (Agent Mode), HashiCorp Terraform, Azure Tools, Bicep.',
      'Install and version-pin OpenTofu and Azure CLI; document supported versions.',
      'Author a devcontainer.json bundling OpenTofu, Azure CLI, tofu/terraform LSP, and shell tooling.',
      'Add .vscode/extensions.json with recommended extensions so the editor prompts on clone.',
      'Write a CONTRIBUTING / SETUP.md with the one-command bootstrap flow.',
      'Validate the container builds clean on a fresh machine (mac + Windows/WSL).',
    ],
    deliverables: [
      'devcontainer.json + Dockerfile',
      '.vscode/extensions.json & settings.json',
      'SETUP.md onboarding guide',
    ],
    exit: 'A new engineer goes from git clone to a working OpenTofu + Azure environment in under 60 minutes, with zero manual tool installs.',
    risks: [
      'Tool version drift across OS — pin everything and test on each platform.',
      'Corporate proxy/firewall blocking container image pulls — pre-mirror images internally.',
    ],
  },
  {
    id: 2,
    icon: Plug,
    accent: 'violet',
    title: 'Add MCP Servers',
    tagline: 'Give the agent eyes and hands: GitHub, Azure, and Terraform over MCP.',
    duration: '~2 weeks',
    owners: 'Platform lead + security reviewer',
    objective:
      'Connect Copilot Agent Mode to live tooling through trusted MCP servers, with secrets handled securely, and prove the agent can read real state and act.',
    tasks: [
      'Create .vscode/mcp.json defining the GitHub, Azure, and Terraform MCP servers.',
      'Route all credentials through input prompts / Key Vault — nothing hardcoded.',
      'Have security review each server before enabling (treat like a dependency).',
      'Smoke-test each server in isolation: query a subscription, search a repo, fetch a module doc.',
      'Run a guided Agent Mode session: "summarise our dev resource group" to confirm tool calls work.',
      'Document the allow-list and how engineers request a new server.',
    ],
    deliverables: [
      '.vscode/mcp.json (committed, secret-free)',
      'Secrets-handling runbook',
      'Approved MCP server allow-list',
    ],
    exit: 'In Agent Mode an engineer can ask a natural-language question that triggers a real Azure query and a GitHub action (e.g. open a draft PR), end to end.',
    risks: [
      'Over-permissioned service principals — start read-only, widen deliberately.',
      'Untrusted third-party servers — only enable reviewed, allow-listed sources.',
    ],
  },
  {
    id: 3,
    icon: BookOpen,
    accent: 'cyan',
    title: 'Author Instructions',
    tagline: 'Encode your IaC, naming, and tagging standards as always-on rules.',
    duration: '~2 weeks',
    owners: 'Senior cloud engineers (standards owners)',
    objective:
      'Capture the team\'s conventions as scoped instruction files so generated code follows your standards automatically, without anyone re-typing them.',
    tasks: [
      'Document current naming convention (<type>-<workload>-<env>) and required tags.',
      'Define region policy, provider-pinning rules, and the no-plaintext-secrets rule.',
      'Write instructions/terraform.md with an applyTo glob scoped to **/*.tf.',
      'Keep rules crisp and testable — short constraints, not essays.',
      'A/B test: generate the same module with and without instructions; compare drift.',
      'Iterate until generated HCL passes review with minimal manual correction.',
    ],
    deliverables: [
      'instructions/terraform.md (scoped via applyTo)',
      'Documented naming + tagging standard',
      'Before/after comparison evidence',
    ],
    exit: 'Code the agent generates conforms to naming, tagging, region, and provider-pinning standards on the first pass, with reviewers making only minor edits.',
    risks: [
      'Instruction bloat diluting model attention — keep them short and rule-like.',
      'Conflicting or stale rules — assign a single standards owner.',
    ],
  },
  {
    id: 4,
    icon: Bot,
    accent: 'blue',
    title: 'Build Skills + Agent Team',
    tagline: 'Reusable procedures plus a planner → implementer → reviewer team.',
    duration: '~3–4 weeks',
    owners: 'Platform team (2–3 engineers)',
    objective:
      'Move from ad-hoc prompting to repeatable workflows: auto-discovered skills for common procedures and a small team of scoped agents that delegate to each other.',
    tasks: [
      'Author skills/opentofu-review/SKILL.md with a clear description for auto-discovery.',
      'Build a read-only iac-planner agent (codebase + azure-mcp + terraform-mcp).',
      'Build an iac-implementer agent that can edit files and run plan/apply.',
      'Define handoffs so the planner delegates to the implementer after approval.',
      'Apply least privilege: only the implementer gets write/apply tools.',
      'End-to-end rehearsal: drive a small landing-zone change through the full team.',
    ],
    deliverables: [
      'skills/ directory (e.g. opentofu-review)',
      'agents/iac-planner.md & iac-implementer.md',
      'Documented handoff workflow',
    ],
    exit: 'The agent team completes a realistic task — plan a dev landing zone, scaffold the .tf files, and self-review — with a human approving the transition between plan and apply.',
    risks: [
      'Agents exceeding scope — enforce least-privilege tool lists per agent.',
      'Skill descriptions too vague to be discovered — write task-matching summaries.',
    ],
  },
  {
    id: 5,
    icon: ShieldCheck,
    accent: 'amber',
    title: 'Add Hooks (Guardrails)',
    tagline: 'Deterministic scripts that always run — formatting, validation, hard stops.',
    duration: '~2 weeks',
    owners: 'Platform + security',
    objective:
      'Layer in non-probabilistic guardrails on lifecycle events so destructive actions are blocked and quality checks run every time — regardless of what the model decides.',
    tasks: [
      'Define hooks/hooks.json with PreToolUse and PostToolUse handlers.',
      'Write guard.sh to block tofu apply without an approved, reviewed plan.',
      'Add a PostToolUse hook to run tofu fmt -recursive after edits.',
      'Test the hard-stop path: confirm a non-zero exit cancels a destructive op.',
      'Wire validation (tofu validate + policy check) into the pre-apply gate.',
      'Document hook behaviour so engineers understand why an action was blocked.',
    ],
    deliverables: [
      'hooks/hooks.json + guard.sh',
      'Pre-apply validation/policy gate',
      'Guardrail behaviour documentation',
    ],
    exit: 'A tofu apply against prod without a reviewed plan is reliably blocked by the hook, and HCL is auto-formatted after every agent edit — with no reliance on the model remembering.',
    risks: [
      'Over-aggressive hooks blocking legitimate work — log clearly and allow override paths.',
      'Hooks not running on all machines — ship them inside the plugin (Phase 6).',
    ],
  },
  {
    id: 6,
    icon: Package,
    accent: 'rose',
    title: 'Package & Publish',
    tagline: 'Bundle everything into one shippable plugin for the whole team.',
    duration: '~2–3 weeks',
    owners: 'Platform lead + enablement',
    objective:
      'Consolidate instructions, skills, agents, MCP servers, and hooks into a single versioned plugin, publish it internally, and drive team-wide adoption.',
    tasks: [
      'Create plugin.json manifest wiring up all six customization layers.',
      'Bundle .mcp.json so servers and hooks travel with the plugin.',
      'Version with semver and write a CHANGELOG.',
      'Publish to your internal registry / shared repo with install instructions.',
      'Run an enablement session and capture a feedback channel.',
      'Define an ownership + update cadence (who maintains, how fixes ship).',
    ],
    deliverables: [
      'Packaged, versioned plugin',
      'Install + usage documentation',
      'Maintenance & ownership plan',
    ],
    exit: 'The whole IT Cloud Team installs one plugin and inherits the full governed setup — standards, agents, and guardrails — with a clear owner and update process in place.',
    risks: [
      'Manifest keys / MCP names drifting with vendor updates — verify against current docs before each release.',
      'Adoption stalling — pair the launch with hands-on enablement, not just a link.',
    ],
  },
];

/* ----------------------------- Detail section ----------------------------- */
function Section({ icon: Icon, label, accent, children }) {
  const a = ACCENTS[accent];
  return (
    <div>
      <div className={`mb-2 flex items-center gap-1.5 text-xs font-semibold uppercase tracking-wider ${a.text}`}>
        <Icon className="h-3.5 w-3.5" />
        {label}
      </div>
      {children}
    </div>
  );
}

function PhaseCard({ phase, open, onToggle }) {
  const a = ACCENTS[phase.accent];
  const Icon = phase.icon;

  return (
    <div className={`overflow-hidden rounded-2xl border ${a.border} bg-slate-800/40 ring-1 ${a.ring}`}>
      {/* Header */}
      <button
        onClick={onToggle}
        className="flex w-full items-center gap-4 px-4 py-4 text-left transition hover:bg-slate-800/40 sm:px-5"
      >
        <div className={`flex h-12 w-12 flex-shrink-0 items-center justify-center rounded-xl bg-gradient-to-br ${a.grad} text-white shadow-lg`}>
          <Icon className="h-6 w-6" />
        </div>
        <div className="min-w-0 flex-1">
          <div className="flex flex-wrap items-center gap-2">
            <span className={`text-xs font-bold uppercase tracking-widest ${a.text}`}>Phase {phase.id}</span>
            <span className="flex items-center gap-1 text-xs text-slate-400"><Clock className="h-3 w-3" />{phase.duration}</span>
          </div>
          <h3 className="mt-0.5 truncate text-lg font-bold text-white sm:text-xl">{phase.title}</h3>
          <p className="mt-0.5 hidden text-sm text-slate-400 sm:block">{phase.tagline}</p>
        </div>
        <ChevronDown className={`h-5 w-5 flex-shrink-0 text-slate-400 transition-transform duration-300 ${open ? 'rotate-180' : ''}`} />
      </button>

      {/* Body */}
      <AnimatePresence initial={false}>
        {open && (
          <motion.div
            initial={{ height: 0, opacity: 0 }}
            animate={{ height: 'auto', opacity: 1 }}
            exit={{ height: 0, opacity: 0 }}
            transition={{ duration: 0.3, ease: 'easeInOut' }}
          >
            <div className="border-t border-slate-700/60 px-4 py-5 sm:px-5">
              {/* Objective */}
              <div className={`mb-5 rounded-xl border ${a.border} ${a.bg} p-3.5`}>
                <Section icon={Target} label="Objective" accent={phase.accent}>
                  <p className="text-sm leading-relaxed text-slate-200">{phase.objective}</p>
                </Section>
              </div>

              <div className="grid gap-5 lg:grid-cols-2">
                {/* Tasks */}
                <div className="lg:col-span-2">
                  <Section icon={ListChecks} label="Task checklist" accent={phase.accent}>
                    <ul className="space-y-2">
                      {phase.tasks.map((t, idx) => (
                        <li key={idx} className="flex items-start gap-2.5 text-slate-200">
                          <CheckCircle2 className={`mt-0.5 h-4 w-4 flex-shrink-0 ${a.text}`} />
                          <span className="text-sm leading-relaxed">{t}</span>
                        </li>
                      ))}
                    </ul>
                  </Section>
                </div>

                {/* Deliverables */}
                <Section icon={FileOutput} label="Deliverables" accent={phase.accent}>
                  <div className="flex flex-wrap gap-2">
                    {phase.deliverables.map((d, idx) => (
                      <span key={idx} className={`rounded-lg border ${a.border} bg-slate-900/60 px-2.5 py-1.5 font-mono text-xs text-slate-200`}>
                        {d}
                      </span>
                    ))}
                  </div>
                </Section>

                {/* Owners */}
                <Section icon={Users} label="Suggested owners" accent={phase.accent}>
                  <p className="text-sm text-slate-200">{phase.owners}</p>
                </Section>

                {/* Exit criteria */}
                <div className="lg:col-span-2">
                  <Section icon={Flag} label="Exit criteria" accent={phase.accent}>
                    <div className="rounded-lg border border-slate-700 bg-slate-900/50 p-3">
                      <p className="text-sm leading-relaxed text-slate-200">{phase.exit}</p>
                    </div>
                  </Section>
                </div>

                {/* Risks */}
                <div className="lg:col-span-2">
                  <Section icon={AlertTriangle} label="Key risks & mitigations" accent="rose">
                    <ul className="space-y-2">
                      {phase.risks.map((r, idx) => (
                        <li key={idx} className="flex items-start gap-2.5">
                          <AlertTriangle className="mt-0.5 h-4 w-4 flex-shrink-0 text-rose-300" />
                          <span className="text-sm leading-relaxed text-slate-300">{r}</span>
                        </li>
                      ))}
                    </ul>
                  </Section>
                </div>
              </div>
            </div>
          </motion.div>
        )}
      </AnimatePresence>
    </div>
  );
}

/* ----------------------------- App ----------------------------- */
export default function App() {
  const [openId, setOpenId] = useState(1);
  const [allOpen, setAllOpen] = useState(false);

  const toggle = (id) => {
    if (allOpen) {
      // when "expand all" is on, clicking just collapses that one isn't tracked; switch to single mode
      setAllOpen(false);
      setOpenId(id);
      return;
    }
    setOpenId((cur) => (cur === id ? null : id));
  };

  const totalWeeks = '13–17 weeks';

  return (
    <div className="min-h-screen w-full bg-slate-900 px-4 py-8 font-sans text-slate-100 sm:px-6 lg:px-8">
      <div className="mx-auto max-w-4xl">
        {/* Header */}
        <div className="mb-6">
          <div className="mb-3 flex items-center gap-2">
            <div className="flex h-9 w-9 items-center justify-center rounded-xl bg-gradient-to-br from-cyan-500 to-violet-500">
              <Layers className="h-5 w-5 text-white" />
            </div>
            <span className="text-sm font-semibold uppercase tracking-widest text-slate-400">IT Cloud Team</span>
          </div>
          <h1 className="text-2xl font-bold text-white sm:text-3xl md:text-4xl">
            Azure IaC Copilot — Adoption Roadmap
          </h1>
          <p className="mt-2 max-w-2xl text-sm text-slate-400 sm:text-base">
            Six sequential phases from a standardized workspace to a shipped, governed Copilot plugin.
            Estimated end-to-end timeline: <span className="font-semibold text-cyan-300">{totalWeeks}</span> with a small platform team.
          </p>

          <div className="mt-4 flex flex-wrap items-center gap-2">
            <button
              onClick={() => setAllOpen((v) => !v)}
              className="rounded-lg border border-slate-700 px-3 py-1.5 text-xs font-medium text-slate-300 transition hover:bg-slate-800"
            >
              {allOpen ? 'Collapse all' : 'Expand all'}
            </button>
            <span className="text-xs text-slate-500">Click any phase to see full detail.</span>
          </div>
        </div>

        {/* Phase rail */}
        <div className="mb-6 flex flex-wrap gap-1.5">
          {PHASES.map((p) => {
            const a = ACCENTS[p.accent];
            const active = !allOpen && openId === p.id;
            return (
              <button
                key={p.id}
                onClick={() => { setAllOpen(false); setOpenId(p.id); }}
                className={`flex items-center gap-1.5 rounded-full px-2.5 py-1 text-xs font-medium transition ${active ? `${a.bg} ${a.text} border ${a.border}` : 'text-slate-400 hover:text-slate-200'}`}
              >
                <span className={`h-2 w-2 rounded-full ${a.dot}`} />
                P{p.id}
              </button>
            );
          })}
        </div>

        {/* Cards */}
        <div className="space-y-3">
          {PHASES.map((p) => (
            <PhaseCard
              key={p.id}
              phase={p}
              open={allOpen || openId === p.id}
              onToggle={() => toggle(p.id)}
            />
          ))}
        </div>

        <p className="mt-8 text-xs text-slate-500">
          Timelines assume a 2–3 person platform team running phases roughly sequentially with some overlap.
          Verify exact plugin manifest keys, MCP server package names, and hook event names against current
          GitHub Copilot &amp; MCP documentation before each release.
        </p>
      </div>
    </div>
  );
}
```

A few notes on the roadmap itself:

The phases are designed to be **sequential but slightly overlappable** — for example, you can start drafting Phase 3 instructions while still hardening Phase 2 MCP connections. I've estimated **13–17 weeks** total for a 2–3 person platform team, but that compresses significantly if you can dedicate more people or if your workspace is already partly standardized.

The structure deliberately front-loads **trust and reproducibility** (workspace, then MCP with security review) before giving the agent more autonomy (skills, agents), and only adds **hard guardrails** (hooks) once you understand the agent's real behavior. Packaging comes last so you're bundling something proven, not shipping guesswork.

Each phase has an explicit **exit criterion** — I'd treat these as go/no-go gates rather than soft targets, since skipping ahead (e.g. granting write/apply tools before hooks exist) is where most teams get burned.

Want me to drop this back into the main slide deck as an expanded multi-slide section, add a Gantt-style timeline visualization, or turn it into a printable one-page checklist your team can track against?
# nl-its-cloud-ai
