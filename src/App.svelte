<script>
	export let name;
	const TIME = ['past', 'present', 'future']
	const ASPECT = ['aorist', 'imperfect', 'perfect']
	const TENSE = ['past_aorist', 'past_imperfect', 'past_perfect', 'present_imperfect', 'future_imperfect']
	const VOICE = ['active', 'mediopassive']
	const MOOD = ['indicative', 'subjunctive', 'optative', 'imperative']
	const NUMBER = ['singular', 'dual', 'plural']
	const PERSON = ['first', 'second', 'third']
	const DICT = {
		'ἀγαπάω': {
			infinitive: {
				active: 'ἀγαπᾶν',
				mediopassive: 'ἀγαπᾶσθαι'
			},
			present_imperfect: {
				active: {
					participle: {
						s: {
							m: {
								nom: 'ἀγαπῶν',
								acc: 'ἀγᾰπῶντᾰ',
								gen: 'ἀγᾰπῶντος',
								dat: 'ἀγᾰπῶντῐ'
							},
							f: {
								nom: 'ἀγᾰπῶσᾰ',
								acc: 'ἀγᾰπῶσᾰν',
								gen: 'ἀγᾰπώσης',
								dat: 'ἀγᾰπώσῃ'
							},
							n: {
								nom: 'ἀγᾰπῶν',
								acc: 'ἀγᾰπῶν',
								gen: 'ἀγᾰπῶντος',
								dat: 'ἀγᾰπῶντῐ'
							}
						},
						p: {
							m: {
								nom: 'ἀγᾰπῶντες',
								acc: 'ἀγᾰπῶντᾰς',
								gen: 'ἀγᾰπώντων',
								dat: 'ἀγᾰπῶσῐ(ν)'
							},
							f: {
								nom: 'ἀγᾰπῶσαι',
								acc: 'ἀγᾰπώσᾱς',
								gen: 'ἀγᾰπωσῶν',
								dat: 'ἀγᾰπώσαις'
							},
							n: {
								nom: 'ἀγᾰπῶντᾰ',
								acc: 'ἀγᾰπῶντᾰ',
								gen: 'ἀγᾰπώντων',
								dat: 'ἀγᾰπῶσῐ(ν)'
							}
						}
					},
					indicative: 'ἀγαπῶ	ἀγαπᾷς	ἀγαπᾷ	ἀγαπᾶτον	ἀγαπᾶτον	ἀγαπῶμεν	ἀγαπᾶτε	ἀγαπῶσῐ(ν)',
					subjunctive: 'ἀγαπῶ	ἀγαπᾷς	ἀγαπᾷ	ἀγαπᾶτον	ἀγαπᾶτον	ἀγαπῶμεν	ἀγαπᾶτε	ἀγαπῶσῐ(ν)',
					optative: 'ἀγαπῴην, ἀγαπῷμῐ	ἀγαπῴης, ἀγαπῷς	ἀγαπῴη, ἀγαπῷ	ἀγαπῷτον, ἀγαπῴητον	ἀγαπῴτην, ἀγαπῳήτην	ἀγαπῷμεν, ἀγαπῴημεν	ἀγαπῷτε, ἀγαπῴητε	ἀγαπῷεν, ἀγαπῴησᾰν',
					imperative: '-	ἀγάπᾱ	ἀγαπᾱ́τω	ἀγαπᾶτον	ἀγαπᾱ́των	- 	ἀγαπᾶτε	ἀγαπώντων',
				},
				mediopassive: {
					indicative: '	ἀγαπῶμαι	ἀγαπᾷ	ἀγαπᾶται	ἀγαπᾶσθον	ἀγαπᾶσθον	ἀγαπώμεθᾰ	ἀγαπᾶσθε	ἀγαπῶνται' ,
					subjunctive: 'ἀγαπῶμαι	ἀγαπᾷ	ἀγαπᾶται	ἀγαπᾶσθον	ἀγαπᾶσθον	ἀγαπώμεθᾰ	ἀγαπᾶσθε	ἀγαπῶνται',
					optative: 'ἀγαπῴμην	ἀγαπῷο	ἀγαπῷτο	ἀγαπῷσθον	ἀγαπῴσθην	ἀγαπῴμεθᾰ	ἀγαπῷσθε	ἀγαπῷντο',
					imperative: '- 	ἀγαπῶ	ἀγαπᾱ́σθω	ἀγαπᾶσθον	ἀγαπᾱ́σθων	 -	ἀγαπᾶσθε	ἀγαπᾱ́σθων'
				}
			}
		}
	}
	let time = 'present'
	let aspect = 'imperfect'
	$: tense = `${time}_${aspect}`
	let voice = 'active'
	let mood = 'indicative'
	let number = 'singular'
	let person = 'first'
	let word = 'ἀγαπάω'
	$: form = DICT[word][tense][voice][mood][number][person]
</script>

<main class="{tense} {voice} {mood} {number} {person}">{word}</main>

<style>
main {
	position: absolute;
	transform:translate(-50%,-50%);
	font-size: 500%;
}
.first { top: 80%; }
.singular { left: 50%; }

</style>


<!--

Active: Present
Indicative
έρχομαι
έρχ-ει
έρχ-εται
ερχ-όμεθα
έρχ-εσθε
έρχ-ονται
Conjunctive
έρχ-ωμαι
έρχ-η
έρχ-ηται
ερχ-ώμεθα
έρχ-ησθε
έρχ-ωνται
Optative
ερχ-οίμην
έρχ-οιο
έρχ-οιτο
ερχ-οίμεθα
έρχ-οισθε
έρχ-οιντο
Imperative
έρχ-ου
ερχ-έσθω
έρχ-εσθε
ερχ-έσθων; ερχ-έσθωσαν
Active: Present
Infinitive
έρχ-εσθαι

Participle
ερχ-όμενος
ερχ-ομένη
ερχ-όμενον
Active: Indicative Past
η-ρχ-όμην
ή-ρχ-ου
ή-ρχ-ετο
η-ρχ-όμεθα
ή-ρχ-εσθε
ή-ρχ-οντο
Active: Future
Indicative
Optative
Active: Future
Infinitive
Participle
Active: Aorist
Past
ή-λθ-ον
ή-λθ-ες
ή-λθ-ε
ή-λθ-ομεν
ή-λθ-ετε
ή-λθ-ον
Conjunctive
έ-λθ-ω
έ-λθ-ης
έ-λθ-η
έ-λθ-ωμεν
έ-λθ-ητε
έ-λθ-ωσι; έ-λθ-ωσιν
Optative
έ-λθ-οιμι
έ-λθ-οις
έ-λθ-οι
έ-λθ-οιμεν
έ-λθ-οιτε
έ-λθ-οιεν
Imperative
ε-λθ-έ
ε-λθ-έτω
ε-λθ-έτε
ε-λθ-έντων
Active: Aorist
Infinitive
ε-λθ-είν

Participle
ε-λθ-ών
ε-λθ-ούσα
ε-λθ-όν
Active: Perfect
Indicative
ελή-λυθ-α
ελή-λυθ-ας
ελή-λυθ-ε; ελή-λυθ-εν
ελη-λύθ-αμεν
ελη-λύθ-ατε
ελη-λύθ-ασι; ελη-λύθ-ασιν
Conjunctive
ελη-λύθ-ω
ελη-λύθ-ης
ελη-λύθ-η
ελη-λύθ-ωμεν
ελη-λύθ-ητε
ελη-λύθ-ωσι; ελη-λύθ-ωσιν
Optative
ελη-λύθ-οιμι
ελη-λύθ-οις
ελη-λύθ-οι
ελη-λύθ-οιμεν
ελη-λύθ-οιτε
ελη-λύθ-οιεν
Active: Perfect
Infinitive
ελη-λυθ-έναι

Participle
ελη-λυθ-ώς
ελη-λυθ-υία
ελη-λυθ-ός
Active: Indicative Pluperfect
ελη-λύθ-ειν
ελη-λύθ-εις
ελη-λύθ-ει
ελη-λύθ-ειμεν
ελη-λύθ-ειτε
ελη-λύθ-εισαν
Medium: Present
Indicative
έρχομαι
έρχ-ει
έρχ-εται
ερχ-όμεθα
έρχ-εσθε
έρχ-ονται
Conjunctive
έρχ-ωμαι
έρχ-η
έρχ-ηται
ερχ-ώμεθα
έρχ-ησθε
έρχ-ωνται
Optative
ερχ-οίμην
έρχ-οιο
έρχ-οιτο
ερχ-οίμεθα
έρχ-οισθε
έρχ-οιντο
Imperative
έρχ-ου
ερχ-έσθω
έρχ-εσθε
ερχ-έσθων; ερχ-έσθωσαν
Medium: Present
Infinitive
έρχ-εσθαι

Participle
ερχ-όμενος
ερχ-ομένη
ερχ-όμενον
Medium: Indicative Past
η-ρχ-όμην
ή-ρχ-ου
ή-ρχ-ετο
η-ρχ-όμεθα
ή-ρχ-εσθε
ή-ρχ-οντο
Medium: Future
Indicative
ελεύ-σομαι
ελεύ-σει
ελεύ-σεται
ελευ-σόμεθα
ελεύ-σεσθε
ελεύ-σονται
Optative
Medium: Future
Infinitive
ελεύ-σεσθαι

Participle
Medium: Aorist
Indicative
Conjunctive
Optative
Imperative
Medium: Aorist
Infinitive
Participle
Medium: Perfect
Indicative
Conjunctive
Optative
Imperative
Medium: Perfect
Infinitive
Participle
Medium: Indicative Pluperfect
Passive: Present
Indicative
έρχομαι
έρχ-ει
έρχ-εται
ερχ-όμεθα
έρχ-εσθε
έρχ-ονται
Conjunctive
έρχ-ωμαι
έρχ-η
έρχ-ηται
ερχ-ώμεθα
έρχ-ησθε
έρχ-ωνται
Optative
ερχ-οίμην
έρχ-οιο
έρχ-οιτο
ερχ-οίμεθα
έρχ-οισθε
έρχ-οιντο
Imperative
έρχ-ου
ερχ-έσθω
έρχ-εσθε
ερχ-έσθων; ερχ-έσθωσαν
Passive: Present
Infinitive
έρχ-εσθαι

Participle
ερχ-όμενος
ερχ-ομένη
ερχ-όμενον
Passive: Indicative Past
η-ρχ-όμην
ή-ρχ-ου
ή-ρχ-ετο
η-ρχ-όμεθα
ή-ρχ-εσθε
ή-ρχ-οντο
Passive: Future
Indicative
Optative
Passive: Future
Infinitive
Participle
Passive: Aorist
Indicative
Conjunctive
Optative
Imperative
Passive: Aorist
Infinitive
Participle
Passive: Perfect
Infinitive
Participle
Passive: Indicative Pluperfect

-->